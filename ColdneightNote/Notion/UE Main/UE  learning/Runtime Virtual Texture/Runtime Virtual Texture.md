# 运行时虚拟纹理（RVT）

在运行时使用GPU按需创建其纹素数据，工作方式与传统纹理映射类似。较大区域上的RVT缓存着色数据非常适用于使用贴花类材质的地形和适配地形的样条。

## 创建一对儿Runtime Virtual Texture 与 Runtime Virtual Builder；

![[Untitled 17.png|Untitled 17.png]]

## 在场景中使用Runtime Virtual Texture Volume的体积工具组件将RVT放置到场景中；

Bounds Align Actor 吸取需要拍摄的actor后，Set Bounds以重新配制Volume大小以匹配actor，除非有特殊需求；对于地形actor，每次更改地形比如刷了深谷或者高山后，需要重新SetBounds；

![[Untitled 1 5.png|Untitled 1 5.png]]

## 配制材质写入数据到RVT中，Runtime Virtual Texture Output输出节点；

![[Untitled 2 6.png|Untitled 2 6.png]]

## 在需要RVT数据的材质中采样RVT资产；

![[Untitled 3 4.png|Untitled 3 4.png]]

## 要注意Virtual Texture Content的设置值，材质中的变量设置与实际的RVT asset值对应

![[Untitled 4 3.png|Untitled 4 3.png]]

## 配制准备好的RVT texture到需要采样点目标Landscape

![[Untitled 5 3.png|Untitled 5 3.png]]

## 测试项目需要采样基础通道和深度两种信息 所以配制了两种RVT，分别对应两个RuntimeVirtualTextureVolume

![[Untitled 6 3.png|Untitled 6 3.png]]

## 两个RVT Volume分别配制创建好的RVT texture和RVT Builder

Build Levels 控制build的低mip等级streaming texture层级数量

当某些设置调整后，会在Build按键旁提示黄色感叹号，需要重新Build RVT Builder，Map Check 同样会触发这个提示；

  

![[Untitled 7 3.png|Untitled 7 3.png]]

## 地形与场景模型穿插混合效果示范

可以用于混合植被 场景内模型等等

也可以通过RVT来降低多层Landscape材质的消耗

![[Untitled 8 3.png|Untitled 8 3.png]]

![[Untitled 9 2.png|Untitled 9 2.png]]

## Shader 性能消耗对比

### 通过Lit列表下的Landscape Visualizers查看Layer的使用情况

![[Untitled 10 2.png|Untitled 10 2.png]]

![[Untitled 11 2.png|Untitled 11 2.png]]

### 总共5 Layers 的复杂地形 RVT性能提升明显；（图2为RVT，图3为普通地形材质）；

![[Untitled 12 2.png|Untitled 12 2.png]]

![[Untitled 13 2.png|Untitled 13 2.png]]

Debug RVT 的控制台命令： stat virtualtexturing