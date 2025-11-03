1.全局光照方式 none
Global Illumination - Dynamic Global Illumination Method   None
![[Pasted image 20251103145042.png]]
2.Lumen的硬件光追 关
 Lumen - Use Hardware Ray Tracing when available    [ ]
![[Pasted image 20251103145119.png]]
3.nanite关掉
Nanite - [ ]

4.关闭距离场  
Generate Mesh Distance Fields [ ]
![[Pasted image 20251103145648.png]]

5.反射模式 选择 None
![[Pasted image 20251103145827.png]]

6.阴影映射模式选择Shadow Maps
![[Pasted image 20251103150010.png]]

7.平台-windows-D3D12 D3D11 开启SM5  Vulkan按需勾选
![[Pasted image 20251103150229.png]]

之后烘焙光照和对应模型的Mobility选择static  
菜单Build选项  **Build Lighting Only**烘焙光照
![[Pasted image 20251103150131.png]]