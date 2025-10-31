在工程config文件夹中的DefaultEngine.ini中加入下列代码

r.Nanite.AllowTessellation=1  
r.Nanite.Tessellation=1

  

![[Untitled 20.png|Untitled 20.png]]

材质新增Displacment节点；

测试模型使用一个开启nanite的10000面的平面；

曲面细分功能需要材质应用的目标模型开启nanite；

![[Untitled 1 8.png|Untitled 1 8.png]]

材质实例的Displaement Scaling 的Magnitude参数 调整曲面细分的强度；

Magnitude = 5

![[Untitled 2 8.png|Untitled 2 8.png]]

Magnitude = 25

![[Untitled 3 6.png|Untitled 3 6.png]]

  

### **Magnitude（幅度）**

- **Magnitude**参数控制位移的强度或幅度。这个值决定了位移映射中各点位移的最大可能距离。较高的Magnitude值会使得位移效果更加明显，而较低的值则会使得效果更为细腻或微妙。
- 在实际应用中，通过调整Magnitude，你可以控制材质的表面细节程度，使其从轻微的纹理变化到极端的几何变形。

### **Center（中心）**

- **Center**参数定义了位移映射中的中点，决定了位移是向模型表面的哪一侧发生。这个值通常在0到1之间，其中0.5通常表示位移映射的中心点，即位移既可以向模型表面的内侧也可以向外侧发生。
- 调整Center值可以改变位移的基准点，进而影响位移映射的视觉效果。例如，将Center设置得更高或更低可以使位移主要向一个方向发展，从而模拟不同的物理效果，如膨胀或收缩。