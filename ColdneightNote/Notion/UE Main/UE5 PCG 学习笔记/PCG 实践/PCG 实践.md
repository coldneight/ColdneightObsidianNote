新建一个PCG Graph，人懒命名NewPCGGraph，丢到有地形的场景里，引擎自动会配置一个PCG Volume在场景里；初上手有点之前的Procedural Foliage Volume的感觉；

点开之后里面默认只有两个节点，红色节点Input、Output；

![[Untitled 22.png|Untitled 22.png]]

Input的引脚可以展开；映入眼帘的绿色引脚 Landscape，鼠标指上去，可以看到说明信息；

![[Untitled 1 10.png|Untitled 1 10.png]]

Provides the landscape represented by this actor if it is a Landscape Proxy, otherwise it returns any landscapes overlapping this actor in the level.

> 具体数据（Concrete Data）是指具体的事物、对象或实例的数据。它包含了实际存在的数值、文字、图像等明确的信息。例如，一个人的年龄、身高、体重等可以作为具体数据。

> 抽象数据（Abstract Data）是对具体数据的抽象和概括。它指的是以更高层次的概念、模型或类别描述的数据。抽象数据不是具体的事物，而是对事物的一种抽象表示。例如，在计算机科学中，栈（Stack）和队列（Queue）可以看作是抽象数据类型，它们定义了一组操作（例如推入、弹出）和相应的行为，但具体的实现可以有多种方式。

> 在数据处理和编程中，我们倾向于使用抽象数据来建立模型和设计算法，以解决更一般化的问题。具体数据则是抽象数据的具体实例，用于实际操作和处理。

总之就是提供一块地形的表面信息；

既然可以获取地形信息，那我们直接拖出来，根据官方文档的示例了解到了**Surface Sampler**节点（一个获取表面信息进行采样撒点的采样器），Settings下有个Points Per Squared Meter参数，能最有效的调节撒点采样密度；

右键选择节点的Node Actions，一个debug，一个Inspect；

![[Untitled 2 10.png|Untitled 2 10.png]]

Debug的效果，会在场景中的PCGVolume中生成用于测试采样点位的debug box；

![[Untitled 3 8.png|Untitled 3 8.png]]

Inspect的用处是当当前PCGGraph作为debug object后，

![[Untitled 4 5.png|Untitled 4 5.png]]

在Attributes列表下可以通过数据表格方式查看所有实际场景内debug点位的信息

![[Untitled 5 5.png|Untitled 5 5.png]]

  

下一个节点 **Transform Points**  
基础设置都是一些对点位的三维参数随机值范围的设置；

![[Untitled 6 5.png|Untitled 6 5.png]]

  

下面是一个随机分布植被的设置参数示例，注意Absoluet Rotation配合只旋转Z轴的旋转范围，意味着随机旋转植被的Z轴角度，但是不左右偏转倒伏，这样让植被在起伏的地形上依然垂直生长分布；

![[Untitled 7 5.png|Untitled 7 5.png]]

![[Untitled 8 4.png|Untitled 8 4.png]]

最后则是布置模型的节点**Static Mesh Spawner**

从节点名字就可以理解，是一个static mesh生成器；映入眼帘的是几个可以配置的参数和一个数组

——**Mesh Entries**；  
默认Selector的Type是PCG Mesh Selector Weighted，基于权重参数去分布数组内的Mesh；

![[Untitled 9 3.png|Untitled 9 3.png]]

这Mesh Entries就是配置要生成模型各种参数的数组；

### 基础小连招

基于以上的基础总结的连接方式，地形表面采样撒点，修改点的属性增加随机性等，根据点位的数据生成制定的模型；

![[Untitled 10 3.png|Untitled 10 3.png]]

  

可以组合多种不同类型的分布器组来创造丰富的植被地块；