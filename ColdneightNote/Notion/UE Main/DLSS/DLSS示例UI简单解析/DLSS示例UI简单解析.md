主要功能都在User Widget BPW_NGX内  

![[Untitled 23.png|Untitled 23.png]]

  

  

  

![[Untitled 1 11.png|Untitled 1 11.png]]

分析UI蓝图内部功能，基本逻辑都是**绑定事件 Bind Event On Selection Changed** 去判定选项修改，之后执行修改UI显示效果和最关键的状态刷新 **函数 Update DLSSDEV Stats；**

这样的逻辑也就意味着修改默认UI的选项之后就会自动更新当前的DLSS策略；

  

![[Untitled 2 11.png|Untitled 2 11.png]]

在UI初始化时基于这三个已经编辑好的枚举内容循环填读取成选项内容，也意味着可以根据需求增加新的可选项；