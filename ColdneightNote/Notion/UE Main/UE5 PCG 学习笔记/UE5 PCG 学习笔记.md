## UE5.2 PCG

在UE5.2中，引入了一种新的Procedural Content Generation（PCG）工具，它可以用于动态地生成地形、建筑、道路等，并可以与其他系统（如Landscape System）集成使用。

PCG工具允许用户使用不同的算法和方法来生成内容，如噪声生成、布朗运动等。用户可以通过选择不同的参数和输入值来定制生成的内容，以满足特定的需求。

该工具还提供了一套完整的蓝图系统，用于控制生成的内容的外观、行为和位置。用户可以自定义蓝图并与PCG系统集成，以实现更高级的控制。

总的来说，UE5.2中的PCG工具提供了一种非常灵活的方式来生成游戏中的内容，并且可以与其他系统集成使用，为游戏开发带来了更多的可能性。

  

==[Procedural Content Generation in Electric Dreams | Unreal Engine 5.2 Documentation](https://docs.unrealengine.com/5.2/en-US/procedural-content-generation-in-electric-dreams/)==

## **术语表**

### **PCG Graph (**PCG图表 **)**

PCG图表是PCG的核心组件，它以图形化的数据流形式来描述一系列操作和逻辑。PCG图表可以保存为子图表，在其他图表中使用。

The **PCG Graph** is the central piece of PCG. A graph describes work through a series of operations performed in the form of a data-flow graph. A PCG Graph can be used inside another graph as a subgraph.

### **PCG Element (PGG元素)**

PGG元素，即PGG图表中的节点。这些元素可以通过C++代码或者PCG蓝图元素类创建。

A **PCG Element** is a node used within a ==[PCG Graph](https://docs.unrealengine.com/5.2/en-US/procedural-content-generation-in-electric-dreams#pcggraph)==. Elements can be created through C++ code or in data using the PCG Blueprint Element class.

### **PCG Settings (PCG设置)**

PCG设置，即节点相关的设置，包括类和Attribute。

**PCG Settings** are the node settings, including its class and set properties.

### **Spatial Data (空间数据)**

空间数据是一种存在于空间中的数据，可以表示体积、2D表面（例如高度场和纹理等）、1D线条（例如样条和点云）。

**Spatial Data** exists in space and can represent:

- Three-dimensional (3D) volumes.
- Two-dimensional (2D) surfaces, such as heightfields and textures.
- One-dimensional (1D) lines, such as splines and point clouds.

### **Point Data (点数据)**

3D空间中的点。每个点都有相关的边界、Property和Attribute信息。它们是操作中最常用的一种PCG数据类型。

**Point Data** represents points in 3D space with associated bounds, defined properties, and attributes. This is the most common PCG data type for operations.

### **Properties (资产)**

点Property是PCG点数据中的一组预定义Property。每个点都有Property。Property可以在Attribute操作中使用，必须以$符号作为前缀。（例如`$Density`, `$Position.x`, `$Rotation.forward`）

Property包括：

●**变换**：变换矩阵：位置（三维向量）、旋转（旋转角度）、缩放（三维向量）

●**密度**：点密度函数的范围是0到1，许多运算过程都会用到这个范围，例如差集、并集、噪点、筛选（浮点）

●**边界最大/最小值**：点边界体积的最大值和最小值（三维向量）

●**颜色**：点的颜色值（四维向量）

●**陡度**：陡度的范围是0到1，表示点密度函数的斜率（浮点）。陡度=1时，密度函数会返回点边界内的最大密度，点边界外为0。陡度<1时，密度函数会返回最大密度值，线性插值最低到0，以点的边界最大/最小值为中心。

●**种子**：由点位置、节点种子和组件种子（int64）计算得到的点种子

Point **Properties** are sets of predefined properties found on all points in PCG [Point Data](https://docs.unrealengine.com/5.2/en-US/procedural-content-generation-in-electric-dreams#pointdata). Properties can be used in attribute operations. Properties must be prefixed with the dollar sign ($), for example, `$Density`, `$Position.x`, `$Rotation.forward`.

These properties are:

- **Transforms**: A transform consisting of a Location (vec3), Rotation (Rotator) and Scale (vec3).
- **Density** (float): A point density function maximum value ranging from 0 to 1. This value is used in multiple operations such as differences, unions, noise, and filtering.
- **BoundsMin/Max** (vec3): Point bounding volume as min and max.
- **Color** (vec4): Point color value.
- **Steepness** (float): A value ranging from 0 to 1 representing the slope of the point's density function. At steepness 1, the density function returns the maximum density within the point's bounds and returns 0 outside. At steepness less than 1, the density function returns maximum density value linearly interpolated down to 0, centered on the point's bounds min/max.
- **Seed** (int64): Point seed computed from point position, node seed, and component seed.

### **Attribute**

Attribute是由用户定义的一组额外metadata，属于某个特定类型；Attribute可以覆盖节点参数或者与点关联，还能用于PCG图表中的Attribute操作。Attribute可以通过“Create Attribute”创建，或者在自定义PCG元素中创建。

An **Attribute** is user-defined, additional metadata of a specific type that can override node parameters, or be associated with points, and used for attribute operations within the ==[PCG Graph](https://docs.unrealengine.com/5.2/en-US/procedural-content-generation-in-electric-dreams#pcggraph)====.== An attribute can be created in the graph using the **Create Attribute** node or within custom ==[PCG Elements](https://docs.unrealengine.com/5.2/en-US/procedural-content-generation-in-electric-dreams#pcgelement)====.==

当前支持的类型仅限于：vec2、vec3、vec4、float、double、int32、int64、bool、string、name、rotator、quaternion;

The supported types for attributes are currently limited to:

- transform
- vec2
- vec3
- vec4
- float
- double
- int32
- int64
- bool
- string
- name
- rotator
- quaternion

### **Assembly (资产集合)**

Assembly是由一组Actor和视效组件拼合而成的单个资产。《Electric Dreams》环境中的Assembly由Quixel资产、关卡实例或打包型关卡Actor组成，手动创建并放置在关卡四处，此外，在Level to PCG资产工具的帮助下，它们也被作为源内容在PCG图表和PCG Assembly中使用。

An **Assembly** is a group of actors and visuals combined to create a single asset. Assemblies in the context of Electric Dreams use Quixel assets combined in Level Instances or Packed Level Actors which are created and placed manually around the level. Assemblies are used as source content in [PCG Graphs](https://docs.unrealengine.com/5.2/en-US/procedural-content-generation-in-electric-dreams#pcggraph) and PCG Assemblies with the help of the Level to PCG asset utility.

### **PCG Assembly**

PCG Assembly是由PCG框架程序化生成的Assembly。PCG Assembly可以通过PCG图表中的一系列操作以多种方式创建，还可以通过更改输入（例如组件和/或公开的参数）进行自定义。PCG Assembly的作用包括生成单个网格体和Actor，以及完全手动制作的Assembly。

A **PCG Assembly** is an assembly that is procedurally generated with the PCG framework. A PCG Assembly can be constructed in multiple ways through a set of operations in a [PCG Graph](https://docs.unrealengine.com/5.2/en-US/procedural-content-generation-in-electric-dreams#pcggraph) and customized by changing their inputs, such as a component or exposed parameters. These operations range from spawning individual meshes and actors to full, handcrafted assemblies.

  

[[PCG 实践]]

[[Mass Entity]]

微信公众号文章

[《Electric Dreams》项目中的程序化内容生成概述 (qq.com)](https://mp.weixin.qq.com/s?__biz=MzAxNzMzODkyMA==&mid=2650671319&idx=1&sn=6dd256c225842921b205138a747d0199&chksm=83edaf90b49a2686d0825eca8bc9c243eca01684b669b4abaa8f9e632c56f15a96af8103f5e6&cur_album_id=2933829730972450817&scene=189#wechat_redirect)

[Electric Dreams PCG技术详解（一）——术语、工具和图表介绍 (qq.com)](https://mp.weixin.qq.com/s?__biz=MzAxNzMzODkyMA==&mid=2650671672&idx=1&sn=a14106d2b96122eee51413334fadbc29&chksm=83edad7fb49a24691522d34cc3e41c31a73665e5eac556d7ec451e9f138fb77223a2f910693a&cur_album_id=2933829730972450817&scene=189#wechat_redirect)

[Electric Dreams PCG技术详解（二）——沟壑、大型Assembly (qq.com)](https://mp.weixin.qq.com/s?__biz=MzAxNzMzODkyMA==&mid=2650671673&idx=1&sn=d3beeeb471073df07fb0f877ef4d493e&chksm=83edad7eb49a24680bfbf0ff3e8dde67caf69723f73051fd899cc8ac5efe5e99f531fd0a9068&cur_album_id=2933829730972450817&scene=189#wechat_redirect)

[Electric Dreams PCG技术详解（三）——森林、岩石和场景背景 (qq.com)](https://mp.weixin.qq.com/s?__biz=MzAxNzMzODkyMA==&mid=2650671674&idx=1&sn=a3e1784af0597aeccf32d618a1fe03dd&chksm=83edad7db49a246b3bbdb85985a80357074491d391c7e0bc446a59017d4561558ff7f3f6411f&cur_album_id=2933829730972450817&scene=189#wechat_redirect)

[Electric Dreams PCG技术详解（四）——远景、雾气、自定义节点及子图表 (qq.com)](https://mp.weixin.qq.com/s?__biz=MzAxNzMzODkyMA==&mid=2650671675&idx=1&sn=bc9fecd503e57b80656230a71ea5168d&chksm=83edad7cb49a246a6184ed0711c7150b07b1006d2c22003ab9f55079253c90b47cdfa389b0da&cur_album_id=2933829730972450817&scene=189#wechat_redirect)