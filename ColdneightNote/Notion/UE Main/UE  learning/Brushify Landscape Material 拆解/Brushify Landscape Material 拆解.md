# 材质系统主要分为三个部分：

![[Untitled 18.png|Untitled 18.png]]

1. 基础分层PBR材质Layer；
    
    材质函数节点MF_LandscapeLayers，里面涵盖了所有基于PBR的算法，基于Layer Blend的不同属性的地面基础材质，以及斜面（例如悬崖峭壁）的材质，还有一些基于视差贴图算法的效果（如雪面）；
    
    同时每个Layer材质通过材质函数 MF_LandscapTillingAndDistance 同步基于距离检测的视觉blend；
    
    在材质函数节点MF_LandscapeLayers内的Layer Blend节点下创建和命名新的分层，如下图中的MySnow；
    
    Slop Mask基于地形表面发现Z轴方向的大小区别斜度，来应用不同的材质；
    
    Flow Map
    
    ![[Untitled 1 6.png|Untitled 1 6.png]]
    
2. Grass 节点 配制的Procedural GrassType ；
    
    ![[Untitled 2 7.png|Untitled 2 7.png]]
    
    Grass 这个节点下可以创建自定义命名的节点，通过LandscapeGrassType资产里面配置好的资产集，通过对应命名的LandScape Layer Sample自定义节点来区分不同的layer；
    
    Brushify材质里面还通过LandScapeLayerSample去减去slop和专门的RemoverRrocedural，在确定最后的资产分布覆盖的范围；（通过参数调整不同斜度的地形植被的有无）;
    
    ![[Untitled 3 5.png|Untitled 3 5.png]]
    
3. RVT系统； RVT系统内容具体见链接：
    
    [[Runtime Virtual Texture]]
    
      
    
    ## 地形材质layers的weight blender layer(normal) 和 no weight blender layer的区别
    
    在Unreal Engine 5 (UE5)中，地形材质的Layers可以通过不同的方式进行混合，以创建复杂且细腻的地形纹理效果。UE5中的地形材质Layers主要分为两种类型：使用Weight Blending的Layers（Normal）和不使用Weight Blending的Layers（No Weight Blended）。
    
    1. **Weight Blended Layer (Normal)**: 使用Weight Blending的Layer允许你通过指定每个Layer的权重来混合多个纹理。权重决定了每个纹理在最终混合中的比例。这种方式非常适合创建自然过渡效果，例如从草地过渡到泥土或岩石。权重的分配可以通过地形绘制工具来动态调整，让艺术家和设计师能更细致地控制地形的外观。
        
        **例子**: 假设你有一个场景，其中包含草地、泥土和岩石三种地形类型。使用Weight Blended Layer，你可以在草地和泥土之间创建一个自然的过渡区，其中草地的权重逐渐减少，而泥土的权重逐渐增加。这样，玩家在游戏中穿越这个区域时，会看到从纯粹的草地平滑过渡到含有部分泥土的草地，最后过渡到完全的泥土地面。
        
    2. **No Weight Blended Layer**: 不使用Weight Blending的Layer不依赖于权重来混合纹理。这种类型的Layer通常用于创建具有明确边界的地形特征，如道路、河流或人造结构。这些Layer直接覆盖在地形上，不与其他Layers混合，或者使用非基于权重的方法来决定如何显示。
        
        **例子**: 假设你想在游戏地图中添加一条道路。使用No Weight Blended Layer，你可以直接在地形上绘制道路纹理，而不需要担心它与周围的草地或泥土纹理混合。这样，道路会清晰地标示出来，与周围环境形成对比，没有模糊的过渡区。
        
    
    **总的来说，Weight Blended Layers适用于需要平滑过渡和自然混合的场景，而No Weight Blended Layers更适用于需要清晰定义和直接覆盖的场景。选择哪种类型取决于你想要实现的视觉效果和场景的具体需求。**