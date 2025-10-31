  

开启硬件光追 path tracing 后期盒子设置

项目设置 render→Support Hardware Ray Tracing 勾选开启硬件光追 需要重启工程

![[Untitled 21.png|Untitled 21.png]]

Translucency Type 选择 Ray Tracing

![[Untitled 1 9.png|Untitled 1 9.png]]

调整Path Tracing参数 Max.Bounces 默认32 普通6-8就好 想要更好的效果可以适当增加参数值；

![[Untitled 2 9.png|Untitled 2 9.png]]

## UE 5.4 新增Movie Render Graph（MRG）功能，可视化编辑Movie Render Queue的设置，并且能将部分设置参数化；

### 配置方式

settings帮忙三角按键下拉后选择Replace with Graph(Experimental)

![[Untitled 3 7.png|Untitled 3 7.png]]

再次点击下拉三角按钮，选择下面现有的配置文件，或者点击New Graph去创建新的配置文件；

![[Untitled 4 4.png|Untitled 4 4.png]]

能配置参数 控制渲染参数变量或者切换渲染模式等，甚至可以通过SubGraph去嵌套配置文件设置；

![[Untitled 5 4.png|Untitled 5 4.png]]

具体使用方式见官方文档

> [!info] Movie Render Graph In Unreal Engine | Unreal Engine 5.4 Documentation | Epic Developer Community  
> Render cinematics using Movie Render Graph MRG in Unreal Engine.  
> [https://dev.epicgames.com/documentation/en-us/unreal-engine/movie-render-graph-in-unreal-engine](https://dev.epicgames.com/documentation/en-us/unreal-engine/movie-render-graph-in-unreal-engine)  

比较详细的使用参考视频

[https://youtu.be/8o2yaZzfHCA?si=2pZ08zXYvZpefe1W](https://youtu.be/8o2yaZzfHCA?si=2pZ08zXYvZpefe1W)

  

### 开启alpha通道的预设配置

Project Setting enable alpha channel support in post processing

![[Untitled 6 4.png|Untitled 6 4.png]]

MRG渲染配置选择**PNG**或者**EXR；**

![[Untitled 7 4.png|Untitled 7 4.png]]