![[Untitled 8.png|Untitled 8.png]]

# ==_**How does Niagara work?**_==

# ==------------------------------------------------------------>==

Niagara runs a series of scripts. We refer to them as Stacks. First, is this blue System Script.

It controls the overall lifecycle of a Particle System. System Spawn controls what happens on the very first frame the system spawns, System Update is the logic which runs every frame thereafter.

Attributes created here are accessible to every other emitter and particle in the system, as data flows from system->emitters->particles.

Niagara 如何工作？

Niagara运行一系列的脚本(Scripts)。我们称它们Stacks。

## 1.首先是蓝色的系统脚本（System Script）

控制粒子系统的整体生命周期；

System Spawn 控制第一帧（the very first frame）发生了什么，生成（Spawn）什么；

System Upadate 控制后面每一帧的逻辑；

这里创建的属性（attributes）可以由系统内所有的发射器和粒子来使用(accessible)，数据流是从 system>emitter>particles;

![[Untitled 1 4.png|Untitled 1 4.png]]

## 2.橘黄色的部分运行系统内的每一个发射器（emitter）；

每一个发射器都有相似的生成和更新脚本；

我们在这里控制系统内每一个发射器的生命周期；

是循环？还是只执行一次？是否允许spawn particles？如果可以，可以spawn多少？本发射器脚本可以用来回答这些问题。

## 3.绿色的是粒子脚本（Particle scripts）；为发射器发射的每一个粒子独立运行；

Particle Spawn 定义生成的时候第一帧的粒子状态；

Particle update 定义生成后每一帧的状态；

两种属性预先已经有许多可用的build或者叫模组（Modules）；通过每一个脚本头右边带颜色的加号box，或者右键点击一个当前已经存在的Module并在当前位置上面或者下面插入新的Module，"insert above" or "insert below"。

## 4.在emitter properties 的 advanced展开选项里 Sim Target选项，开启 Simulation Stages On GPU eimtter

![[Untitled 2 5.png|Untitled 2 5.png]]

![[Untitled 3 3.png|Untitled 3 3.png]]

![[Untitled 4 2.png|Untitled 4 2.png]]

## 5.Emitter Setting -> Sim Target 整个粒子系统的执行分区

CPU/GPU  大部分两种模式都适用，但是展现效果不同；

例如，在GPU模拟下  碰撞的处理更效率，但是相较于CPU模式不够精确， 某些Render模式只适用于CPU : Ribbon、Light；

GPU simulation 在处理大量粒子的情况下性能表现更好；

![[Untitled 5 2.png|Untitled 5 2.png]]

## 6.Render : Renderer Bindings 可以通过引用其他的attributes去overwritten

Material Parameter Bindngs:

根据Array下elements 的material  给每一个粒子创建dynamic material instance  ，并通过Niagara Simulation Variables列出的参数去给动态材质实例的parameters 赋值

![[Untitled 6 2.png|Untitled 6 2.png]]

## 7.Transient 瞬间（短暂/实时）变量

创建新的Particle Attribute 右键 Change Namespace to TRANSIENT

![[Untitled 7 2.png|Untitled 7 2.png]]

![[Untitled 8 2.png|Untitled 8 2.png]]

A transient Value which can be written to and read from any module;

Transient  values do not persist from frame to frame, or between stages;

不保存到下一帧，也不保存到下一阶段的运算。

点开眼镜  可以看到Stage Transients下的创建的新变量

## 8.Module Outputs

![[Untitled 9.png]]

紫色的mark说明Module Outputs是 Transient Outputs, 不会存储在payload里面、不会经过内存堆栈；

Particle Spawn 的 Output 无法再 Particle Update 中获取 ; 前后帧不继承，不持续存在。

## 9.Scratch Pad

类比模块化的Niagara Module Script 之于 Actor的BP下些功能逻辑；Scrathc Pad 类似于关卡蓝图快速搭建功能；如果要模块化还是在Module Script上重构。

## 10.ID: 三种不同的获取 particle id的途径

Particles.ID

Particles.UniqueID

Execution Index

## 11.Namespace & NameSpace Modifier 命名空间&命名空间修饰符

![[Untitled 10.png]]

![[Untitled 11.png]]

System    Emitter    Output    StackContext    Transient  Particles

System  修饰的变量 是 持续变量 persistent attribute , 只能在system堆栈阶段进行设置修改   can be read anywhere

Eimtter  persistent attribute, 在 Eimtter stage 写入 ，

can be read  in Eimtter & Particle stage;

Particles   persistent attribute ,  能在particle stage 读取和写入;

## 12. User Exposed

Exp :  在 particle spawn 下 采样sample static mesh 并 Link Inputs to User Exposed paramater

在System Settings 下设置默认的参数属性

## 13. Simulation Stages

在Emitter Setting下的 Emitter properties 内——————Simulation Stages

之后在粒子堆栈下能增加新的 simulation stage

![[Untitled 12.png]]

之后在Simulation Stage Name栏中修改名字

可以在simulation stage 下增加 niagara module script 或者 scratch pad module

![[Untitled 13.png]]

## 14.Grid 2D

新建一个Vector2D Emitter Attribute  并set

设置GRID的分辨率，勾选Preview Attribute

在simulation stage 下新增 scratch pad

Simulation Stage Iteration Source 选择Data Interface  并配置变量位Grid2D

Scratch pad Moudle 的本地Input Grad 2D collection 变量配置位Grid2D

Scratch Pad下

Execution Index to Unit 将二维的0-127的grid数值转换成0-1的Vector2D UV

![[Untitled 14.png]]

可以在Preview窗口下看到 两个 0-1 的区间 渐变

将Unit的{(0,1)(0,1)}进行如下处理 " *2 -(1,1) "  得到(-1,1)的渐变

![[Untitled 15.png]]

## 15.Attribute Reader

Attribute Reader is used to copy position and velocity atrrirbutes across form one emitter ot nother emitter.

属性读取器   Particle Read 填写需要读取的target

Get Num Particles  返回buffer中粒子的数量  Num Particles ;

(0, Num Particles -1 ) 区间是当前粒子集合的ID区间;

Calculate Random Range Integer 获取随机的Particle ID  之后 根据 particle ID 获取 Attribute Reader 中的 Position ;

Position +offset --->Set Followers 每个粒子 的 position;

## 16. NeighborGrid

NeighborGrid.SimulationToUnit(Position, SimulationToUnit, UnitPos)

NeighborGrid.UnitToIndex(UnitPos, Index.x,Index.y,Index.z)

NeighborGrid.GetNumCells(NumCells.x, NumCells.y, NumCells.z)

NeighborGrid.IndexToLinear(Index.x, Index.y, Index.z, LinearIndex)

NeighborGrid.MaxNeighborsPerCell(MaxNeighborsPerCell)

NeighborGrid.SetParticleNeighborCount(LinearIndex, 1, PreviousNeighborCount)

NeighborGrid.NeighborGridIndexToLinear(Index.x, Index.y, Index.z, PreviousNeighborCount, NeighborGridLinear)

NeighborGrid.SetParticleNeighbor(NeighborGridLinear, ExecIndex, IGNORE)

## 17.Custom HLSL

多用于执行循环和部分为暴露的函数

在节点上定义了输入和输出 float 类型的 spacing 和float3的 PointLocation，则无需在hlsl code 中定义;

  

  

## 18. inital parameters

Particle INITIAL parameters

调用的是spwan的时候的初始值 不会随着时间变化而改变的值；

![[Untitled 16.png]]