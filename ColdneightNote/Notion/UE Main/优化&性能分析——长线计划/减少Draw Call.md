  

**epic工程师的回答：**

Instanced meshes will reduce the draw call overhead on the CPU but will not reduce the GPU cost. In fact the GPU time can increase when using instancing. Allow me to get a little technical for a moment:

This process has to do with the limitations of the CPU vs. GPU and how the API (OpenGL or DirectX) tries to maximize this limitation through batching. Instancing being a special case of batching. With a scene rendered with many small or simple objects each with only a few triangles, the performance is entirely CPU-bound by the API; the GPU has no ability to increase it. More precisely, "the processing time on the CPU for the draw call is greater than the amount of time the GPU takes to actually draw the mesh, so the GPU is starved." [Moeller, Real Time Rendering, 708]. So Batching attempts to allow the CPU to combine a number of objects into a single API call. In the case of Instancing it is the one mesh and the number of times you are drawing with a separate data structure for holding information about each separate mesh.

From a Rendering Engineerer:

"On meshes and material IDs, let me present a hypothetical situation to try to explain the situation more clearly. Let's say you have a mesh that has three materials: wood, chrome, and leather. Now let's say you place 100 of these meshes in your level. Ignoring other passes (shadow, depth only), this will result in 300 draw calls: one per-ID, per-instance. You can see this by looking at the section counts in the primitive stats window.

First thing to keep in mind: some draw calls are more expensive than others. The renderer sorts by material. So in this hypothetical scene we will draw the 100 wood elements first, the 100 chrome elements next, and the 100 leather elements last. Once we draw a wood element, the cost of drawing another wood element is not so high because we are rendering using the same shader and with mostly the same textures. But once we switch materials to draw the chrome we incur a high cost. That's why the renderer sorts by material.

Compare that situation to another scene where you have the same mesh instanced 100 times but each mesh has its own unique material. The scene is still 300 draw calls but the renderer incurs the material switch cost for every draw call. Instancing a mesh provides performance benefits even if the total number of draw calls does not reflect that"

To really see the performance boost in using Instances bring up the Stat UNIT and watch the DRAW versus GPU (CPU vGPU) and notice when you instance a mesh the CPU time remains fairly consistent depending on the additional information you are wanting to pass to each instance, while the GPU will increase. All of these numbers are still dependent on the size of your mesh and the type of material setup and the ultimate limitations of your CPU and GPU.

Thank You

Eric Ketchum

# 减少Draw Call

**epic工程师的回答：**

实例化网格将减少CPU上的绘制调用开销，但不会减少GPU成本。实际上，使用实例化时，GPU时间可能会增加。让我稍微讲一下技术细节：

这个过程涉及到CPU与GPU的限制以及API（OpenGL或DirectX）如何通过批处理来最大化这个限制。实例化是批处理的一种特殊情况。对于一个场景，如果渲染了许多带有只有几个三角形的小而简单的物体，性能完全受限于API的CPU绑定；GPU无法提高性能。更准确地说，“绘制调用在CPU上的处理时间大于GPU实际绘制网格的时间，因此GPU处于饥饿状态。”[Moeller，《实时渲染》（Real Time Rendering），708]。因此，批处理试图允许CPU将多个对象组合成单个API调用。在实例化的情况下，是一个网格和你用于保存每个单独网格信息的单独数据结构的绘制次数。

从渲染工程师的角度出发：

“关于网格和材质ID，让我提出一个假设的情况，试图更清楚地解释这个情况。假设您有一个网格，它有三种材质：木材、铬和皮革。现在假设您在您的级别中放置了100个这样的网格。忽略其他通行证（阴影、仅深度），这将导致300个绘制调用：每个ID、每个实例一个。您可以通过查看原始统计数据窗口中的部分计数来看到这一点。

首先要记住的是，一些绘制调用比其他绘制调用更昂贵。渲染器按材质进行排序。因此，在这个假想场景中，我们将首先绘制100个木制元素，接下来绘制100个铬元素，最后绘制100个皮革元素。一旦我们绘制了一个木制元素，绘制另一个木制元素的成本就不那么高了，因为我们使用相同的着色器并且使用大多相同的纹理进行渲染。但是一旦我们切换材质以绘制铬，我们就会产生很高的成本。这就是为什么渲染器按材质排序的原因。

将此情况与另一个场景进行比较，在该场景中，您将同一个网格实例化100次，但每个网格都有自己独特的材质。场景仍然是300个绘制调用，但渲染器会为每个绘制调用产生材质切换成本。即使绘制调用的总数不反映这一点，实例化网格也提供了性能优势。”

要真正看到使用实例化的性能提升，请打开Stat UNIT并观察DRAW与GPU（CPU vGPU）之间的比较，并注意当您实例化网格时，CPU时间保持相对稳定，具体取决于您想要传递给每个实例的其他信息，而GPU将增加。所有这些数字仍然取决于您的网格大小、材质设置类型以及CPU和GPU的最终限制。

谢谢

Eric Ketchum  
<insert-here/>

  

  

l