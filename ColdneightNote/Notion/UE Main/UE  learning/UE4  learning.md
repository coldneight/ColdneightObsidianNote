# UE4 引擎教学重点分析

本文旨在分析UE4引擎教学过程中的重点，以帮助学习者更好地掌握UE4引擎的核心知识点。

## 1. UE4引擎基础

UE4引擎的基础知识是学习UE4的必备前提，包括：

- UE4引擎的概述
- UE4引擎的安装与配置
- UE4编辑器的界面与布局
- UE4的基本操作和快捷键

## 2. UE4蓝图系统

UE4蓝图系统是UE4引擎中一个重要的可视化编程工具，需要重点掌握以下知识点：

- 蓝图系统的概述和基本原理
- 蓝图系统中的数据类型和控制节点
- 蓝图系统中的流程控制和逻辑运算
- 蓝图系统中的函数和事件

## 3. UE4材质系统

UE4材质系统是UE4引擎中一个非常强大的渲染工具，需要重点掌握以下知识点：

- 材质系统的概述和基本原理
- 材质系统中的材质节点和纹理节点
- 材质系统中的参数化和实例化
- 材质系统中的动态材质和材质实例

## 4. UE4关卡设计

UE4关卡设计是UE4引擎中一个非常重要的环节，需要重点掌握以下知识点：

- 关卡设计的概述和基本原理
- 关卡设计中的场景制作和地形编辑
- 关卡设计中的灯光和后处理
- 关卡设计中的碰撞体和触发器

## 5. UE4代码开发

UE4代码开发是UE4引擎中一个非常高级的技能，需要重点掌握以下知识点：

- UE4代码开发的概述和基本原理
- UE4代码开发中的C++语言和UE4 API
- UE4代码开发中的游戏逻辑和网络编程
- UE4代码开发中的插件开发和打包发布

以上是UE4引擎教学中的重点内容，希望本文能对UE4引擎学习者有所帮助。

  

  

  

很抱歉，您的问题与此文档无关。本文档旨在分析UE4引擎教学的重点内容，涵盖UE4基础、蓝图系统、材质系统、关卡设计和代码开发等方面。如果您有UE5 GPU使用率方面的问题，建议您查阅相关文献或咨询专业人士。

  

  

  

要设置动态光场景的反射球，您需要使用反射球体积材质。请按照以下步骤操作：

1. 在场景中创建一个球体，并将其放置在您想要反射光的位置上。
2. 将球体的材质设置为反射球体积材质。
3. 在场景中添加一个反射球体积组件，并将其放置在您想要反射光的位置上。
4. 将反射球体积组件的材质设置为您创建的反射球体积材质。

通过这些步骤，您就可以设置动态光场景的反射球了。如果您需要更详细的信息，请参考UE4文档中有关反射球体积材质和反射球体积组件的内容。

  

很抱歉，我不理解您的问题。但是，如果您想要在场景中自动同步动态反射球的效果，您可以尝试使用UE4的蓝图系统和材质系统。通过蓝图，您可以创建一个可以自动同步反射球体积材质的脚本。同时，通过材质系统，您可以设置反射球体积材质的参数，以达到您想要的效果。如果您需要更详细的信息，请参考UE4文档中有关蓝图系统和材质系统的内容。

  

要在UE4中使用蓝图控制反射球体积材质的cube map，您需要执行以下步骤：

1. 点击反射球体积组件，在Details面板中找到Material节点，并单击其右侧的编辑按钮。这将打开材质编辑器。
2. 在材质编辑器中，添加一个TextureObjectParameter节点，并将其命名为CubeMap。
3. 添加一个DynamicMaterialInstance节点，并将其连接到反射球体积的Material节点上。将TextureObjectParameter节点连接到DynamicMaterialInstance节点的Texture节点上。
4. 在蓝图中创建一个变量，作为TextureObjectParameter节点的输入。
5. 创建一个MaterialParameterCollection对象，并将其添加到您的蓝图中。将TextureObjectParameter节点的CubeMap属性绑定到MaterialParameterCollection对象的相应参数上。
6. 在蓝图中创建一个动态材质实例，并将其连接到反射球体积的DynamicMaterialInstance节点上。将您创建的MaterialParameterCollection对象连接到动态材质实例的Collection节点上。将您创建的变量连接到动态材质实例的TextureObject节点上。

通过这些步骤，您就可以使用蓝图控制反射球体积材质的cube map了。如果您需要更详细的信息，请参考UE4文档中有关蓝图系统和材质系统的内容。

  

  

UE4 Sphere Reflection Capture 是一种动态捕捉反射的方法，可以在运行时捕捉场景中的反射，并将其应用于材质中。其基本原理是将球形反射捕捉器放置在场景中，该捕捉器会捕捉周围环境的反射，并将其存储在球形纹理中。然后，可以将该纹理应用于材质中，以模拟场景中的反射。在运行时，球形反射捕捉器将动态地更新其反射，以反映场景中的变化。通过使用多个球形反射捕捉器，可以捕捉场景中更广泛的反射，并将其应用于更复杂的材质中。

要在UE4中使用蓝图控制反射球体积材质的cube map，您需要执行以下步骤：

1. 点击反射球体积组件，在Details面板中找到Material节点，并单击其右侧的编辑按钮。这将打开材质编辑器。
2. 在材质编辑器中，添加一个TextureObjectParameter节点，并将其命名为CubeMap。
3. 添加一个DynamicMaterialInstance节点，并将其连接到反射球体积的Material节点上。将TextureObjectParameter节点连接到DynamicMaterialInstance节点的Texture节点上。
4. 在蓝图中创建一个变量，作为TextureObjectParameter节点的输入。
5. 创建一个MaterialParameterCollection对象，并将其添加到您的蓝图中。将TextureObjectParameter节点的CubeMap属性绑定到MaterialParameterCollection对象的相应参数上。
6. 在蓝图中创建一个动态材质实例，并将其连接到反射球体积的DynamicMaterialInstance节点上。将您创建的MaterialParameterCollection对象连接到动态材质实例的Collection节点上。将您创建的变量连接到动态材质实例的TextureObject节点上。

通过这些步骤，您就可以使用蓝图控制反射球体积材质的cube map了。如果您需要更详细的信息，请参考UE4文档中有关蓝图系统和材质系统的内容。

UE4 Sphere Reflection Capture 是一种动态捕捉反射的方法，可以在运行时捕捉场景中的反射，并将其应用于材质中。其基本原理是将球形反射捕捉器放置在场景中，该捕捉器会捕捉周围环境的反射，并将其存储在球形纹理中。然后，可以将该纹理应用于材质中，以模拟场景中的反射。在运行时，球形反射捕捉器将动态地更新其反射，以反映场景中的变化。通过使用多个球形反射捕捉器，可以捕捉场景中更广泛的反射，并将其应用于更复杂的材质中。

  

  

UE4支持的音频格式包括：WAV、MP3、OGG和FLAC。其中，WAV和MP3是最常用的音频格式，OGG和FLAC通常用于游戏开发中需要压缩音频文件大小的情况。

  

要在UE4中使用媒体播放器控制UI界面中的播放进度，您可以按照以下步骤操作：

1. 在UMG中创建一个Slider控件，并将其添加到您的UI界面中。
2. 在蓝图中创建一个媒体播放器对象，并将其连接到您的Slider控件上。
3. 在蓝图中创建一个变量，作为Slider控件的输入。
4. 在蓝图中创建一个定时器，并将其连接到媒体播放器对象的当前时间节点上。将定时器的时间间隔设置为您希望更新Slider的时间间隔。
5. 在蓝图中创建一个事件，以响应Slider控件的值更改。将Slider控件连接到该事件上，并将Slider的值作为媒体播放器对象的当前时间输入。
6. 在蓝图中创建一个事件，以响应媒体播放器对象的状态更改。将媒体播放器对象连接到该事件上，并在事件中更新Slider控件的最大值和当前值，以反映媒体播放器的状态。

通过这些步骤，您就可以使用媒体播放器控制UI界面中的播放进度了。如果您需要更详细的信息，请参考UE4文档中有关媒体播放器和UMG的内容。

UE4中可以使用以下方法来降低drawcall：

1. 合并网格：将多个网格合并为一个网格，可以减少drawcall数量。
2. 减少材质数量：使用尽可能少的材质数量，可以减少drawcall数量。
3. 减少材质特性：减少材质特性（如透明度、反射等），可以减少drawcall数量。
4. 使用LOD：使用LOD（Level of Detail）技术，可以根据距离和屏幕空间大小来动态切换不同的网格和材质，从而减少drawcall数量。
5. 批处理：在一个drawcall中尽可能多地绘制物体，可以减少drawcall数量。
6. 优化光照：减少光照数量和质量，可以减少drawcall数量。
7. 使用Instanced Static Mesh：使用Instanced Static Mesh技术，可以通过一次drawcall绘制许多相同的网格，从而减少drawcall数量。
8. 使用Instanced Material：使用Instanced Material技术，可以通过一次drawcall绘制许多相同的材质，从而减少drawcall数量。

以上是UE4中降低drawcall数量的一些常用方法，可以根据具体情况选择合适的方法进行优化。

材质系统可以对drawcall数量产生影响。在材质编辑器中，您可以使用Material Instance Dynamic节点来创建一个可以在运行时更改材质属性的材质实例。通过创建材质实例，您可以使用较少的材质来渲染场景中的多个物体，从而减少drawcall数量。此外，减少材质中的特性（如透明度和反射）也可以减少drawcall数量。如果您需要更详细的信息，请参考UE4文档中有关材质系统和drawcall优化的内容。

在UE4中，drawcall指的是GPU绘制一个物体所需的调用次数。每个drawcall都需要进行一次CPU到GPU的调用，因此较多的drawcall数量会降低游戏的性能。材质和材质实例可以对drawcall数量产生影响。在材质编辑器中，您可以使用Material Instance Dynamic节点来创建一个可以在运行时更改材质属性的材质实例。通过创建材质实例，您可以使用较少的材质来渲染场景中的多个物体，从而减少drawcall数量。此外，减少材质中的特性（如透明度和反射）也可以减少drawcall数量。如果您需要更详细的信息，请参考UE4文档中有关材质系统和drawcall优化的内容。

  

在UE4中，一个母材并不一定对应一个drawcall。一个母材可以被多个物体使用，这些物体可以在一个drawcall中一起被渲染。另一方面，如果一个母材被多个物体使用，但是这些物体需要分别进行渲染，那么这个母材就对应了多个drawcall。此外，使用材质实例可以在运行时更改材质属性，从而避免为每个物体创建不同的母材。这可以进一步减少drawcall数量，提高游戏性能。

在UE4中，一个母材可以被多个物体使用，这些物体可以在一个drawcall中一起被渲染。这意味着，如果多个模型使用同一个材质，则这些模型可以一起被渲染，从而减少drawcall数量。然而，如果同一个材质被多个物体使用，但是这些物体需要分别进行渲染，那么这个母材就对应了多个drawcall，从而增加了渲染的负担。

因此，可以通过优化材质使用和创建材质实例来降低drawcall数量。使用材质实例可以在运行时更改材质属性，从而避免为每个物体创建不同的母材，进一步减少drawcall数量，提高游戏性能。此外，减少材质中的特性（如透明度和反射）也可以减少drawcall数量。因此，在创建模型时，应该尽可能简化材质的数量和特性，以减少drawcall数量，提高游戏性能。

总之，模型的材质数量和drawcall之间没有一对一的对应关系，而是受多种因素影响。优化材质使用和创建材质实例可以有效地降低drawcall数量，提高游戏性能。

  

增加模型面数会对CPU和GPU效率产生不同的影响。对于CPU而言，它需要更多的计算来处理更多的面数，因此增加面数会降低CPU效率。对于GPU而言，它需要更多的存储和处理来渲染更多的面数，因此增加面数会降低GPU效率。因此，在开发中，需要在CPU和GPU之间进行权衡，以确保模型具有足够的细节和逼真度，同时不会降低游戏性能。此外，可以使用一些技术来优化模型面数，例如使用LOD技术，在远处使用较少的面数来代替较高的面数，从而减少对CPU和GPU的负荷。

  

  

  

  

UE4中的Camera Relative World Space是相对于摄像机位置的世界坐标系。在这个坐标系中，摄像机的位置为原点，摄像机的方向为Z轴正方向。因此，可以使用Camera Relative World Space来计算物体相对于摄像机的位置和方向，以实现一些特殊的效果，例如在摄像机移动时保持物体位置不变，或者在摄像机旋转时保持物体朝向不变等。如果您需要更详细的信息，请参考UE4文档中有关坐标系和摄像机的内容。

  

  

  

在UE4中，隐藏一个关卡可能会对drawcall数量产生影响，但是卸载一个关卡可以显著降低drawcall数量。当隐藏一个关卡时，该关卡中的物体仍然存在于场景中，只是不再被绘制。因此，隐藏一个关卡不会改变场景中的物体数量，也不会改变drawcall数量。但是，如果一个关卡被完全卸载，则该关卡中的物体将不再存在于场景中，drawcall数量也会相应减少。因此，在优化游戏性能时，应该尽可能使用关卡卸载来管理场景中的物体数量，从而减少drawcall数量。如果您需要更详细的信息，请参考UE4文档中有关关卡管理和drawcall优化的内容。

要分析UE4的ue4stats profile性能文件，请按照以下步骤操作：

1. 在UE4编辑器中，打开要分析的项目。
2. 在命令行中输入“stat startfile”命令，并运行项目。这将启用性能分析。
3. 在项目中进行一些操作，例如播放游戏或编辑场景。
4. 在命令行中输入“stat stopfile”命令，停止性能分析。这将生成一个ue4stats profile性能文件，该文件包含了项目运行期间的性能数据。
5. 在UE4编辑器中，打开“Windows”菜单，并选择“开发者工具”>“性能分析器”。
6. 在性能分析器窗口中，单击“打开文件”按钮，并选择刚刚生成的ue4stats profile性能文件。
7. 在性能分析器窗口中，您可以查看各种性能数据，例如CPU和GPU使用率、drawcall数量、内存使用情况等。您还可以比较不同的性能数据，例如在两个不同的时间点之间的CPU使用率等。

通过分析ue4stats profile性能文件，您可以了解项目的性能瓶颈，并采取相应的措施来优化游戏性能。如果您需要更详细的信息，请参考UE4文档中有关性能分析器和ue4stats profile性能文件的内容。

  

在UE4中，性能分析器可以用来分析项目的性能瓶颈，并找到优化游戏性能的方法。性能分析器可以显示多个线程的性能数据，每个线程都对应着项目中的一个进程。要区分性能分析工具显示的线程并与工程的进程对应，可以按照以下步骤操作：

1. 在性能分析器窗口中，单击“线程”选项卡。这将显示当前项目中所有的线程。
2. 找到您要分析的线程，并记录其ID。您可以根据线程名称、CPU使用率等信息来找到目标线程。
3. 在UE4编辑器中，打开命令行，并输入“tlist”命令。这将显示当前系统中所有的进程及其ID。
4. 找到与您要分析的线程对应的进程，并记录其ID。您可以根据进程名称、ID等信息来找到目标进程。
5. 在性能分析器窗口中，右键单击目标线程，并选择“关联进程”选项。然后，输入与目标进程对应的ID，并单击“确定”按钮。
6. 现在，您就可以在性能分析器中查看该线程的性能数据，并与项目中的进程对应了。

通过以上步骤，您就可以区分性能分析工具显示的线程，并将其与工程的进程对应起来，以便更好地分析项目的性能瓶颈。如果您需要更详细的信息，请参考UE4文档中有关性能分析器和线程的内容。

|   |   |
|---|---|
|线程名称|UE4功能|
|GameThread|游戏逻辑和渲染|
|RenderThread|渲染和渲染资源处理|
|SlateThread|UI渲染|
|AudioThread|音频处理|
|AsyncLoadingThread|资源异步加载|
|PhysXThreadPool|物理模拟|
|TaskGraphThread|游戏任务|

|   |   |
|---|---|
|线程名称|UE4功能|
|GameThread|游戏逻辑和渲染|
|RenderThread|渲染和渲染资源处理|
|SlateThread|UI渲染|
|AudioThread|音频处理|
|AsyncLoadingThread|资源异步加载|
|PhysXThreadPool|物理模拟|
|TaskGraphThread|游戏任务|

以上是UE4性能分析工具列出的线程与UE4功能的对应关系表。在UE4中，不同的线程负责不同的任务，例如GameThread负责游戏逻辑和渲染，RenderThread负责渲染和渲染资源处理，SlateThread负责UI渲染等。通过了解不同线程的功能，可以更好地分析和优化游戏性能。

GameThread有以下子线程：

- TaskGraphThread（游戏任务）
- AsyncLoadingThread（资源异步加载）
- PhysXThreadPool（物理模拟）
- AudioThread（音频处理）

RenderThread有以下子线程：

- SceneCaptureThread（场景捕捉）
- RHICommandThread（渲染命令）
- RHIThread（渲染资源处理）
- AsyncComputeThread（异步计算）
- GPUSkinCacheThread（GPU皮肤缓存）
- RenderThreadTaskGraph（渲染任务）

TaskGraphThread有以下子线程：

- AsyncLoadingThread（资源异步加载）
- PhysXThreadPool（物理模拟）
- AudioThread（音频处理）

  

  

|   |   |
|---|---|
|线程名称|UE4功能|
|GameThread|游戏逻辑和渲染|
|RenderThread|渲染和渲染资源处理|
|SlateThread|UI渲染|
|AudioThread|音频处理|
|AsyncLoadingThread|资源异步加载|
|PhysXThreadPool|物理模拟|
|TaskGraphThread|游戏任务|

以上是UE4性能分析工具列出的线程与UE4功能的对应关系表。在UE4中，不同的线程负责不同的任务，例如GameThread负责游戏逻辑和渲染，RenderThread负责渲染和渲染资源处理，SlateThread负责UI渲染等。通过了解不同线程的功能，可以更好地分析和优化游戏性能。

GameThread有以下子线程：

- TaskGraphThread（游戏任务）
- AsyncLoadingThread（资源异步加载）
- PhysXThreadPool（物理模拟）
- AudioThread（音频处理）

RenderThread有以下子线程：

- SceneCaptureThread（场景捕捉）
- RHICommandThread（渲染命令）
- RHIThread（渲染资源处理）
- AsyncComputeThread（异步计算）
- GPUSkinCacheThread（GPU皮肤缓存）
- RenderThreadTaskGraph（渲染任务）

TaskGraphThread有以下子线程：

- AsyncLoadingThread（资源异步加载）
- PhysXThreadPool（物理模拟）
- AudioThread（音频处理）

AudioThread是UE4的主线程之一，负责处理音频相关任务，例如混音、音频效果处理等。在GameThread和RenderThread中，也会包含一些与音频相关的子线程，例如在GameThread中的AudioThread子线程负责处理音频资源加载和释放，而在RenderThread中的AudioMixerThread子线程负责混音。

需要注意的是，一个线程可以包含多个子线程，每个子线程又可以有自己的子线程，因此一个线程既可以是主线程，又可以是子线程。在UE4中，主线程通常会包含多个子线程，这些子线程负责处理不同的任务，以提高游戏的效率和性能。

如果您需要更详细的信息，请参考UE4文档中有关线程、主线程和子线程的内容。

在UE4中，FFileTransferRunnable是一个用于处理文件传输的子线程。它负责将文件从磁盘读取到内存中，或将内存中的文件写入到磁盘中。在UE4的资源管理系统中，FFileTransferRunnable线程通常用于异步加载资源文件，以提高游戏的加载速度和性能。如果您需要更详细的信息，请参考UE4文档中有关线程和资源管理的内容。

CPU Stall-Sleep是一种用于等待CPU资源的进程。在UE4中，CPU Stall-Sleep进程通常是由于某些任务需要等待CPU资源而导致的，例如等待资源加载完成或等待其他任务完成。当CPU Stall-Sleep进程处于等待状态时，它会将CPU资源释放给其他进程，以提高游戏的整体性能。如果您需要更详细的信息，请参考UE4文档中有关CPU Stall-Sleep和进程管理的内容。

![[Untitled 2.png|Untitled 2.png]]

在UE4中，Frame Sync Time是一种性能指标，用于衡量CPU和GPU之间的同步时间。它表示CPU在等待GPU完成渲染的时间，通常是以毫秒为单位计算。Frame Sync Time越低，游戏的帧率和响应速度就越高。

  

UE4 Other TaskGraph Tasks 包含以下线程:

- AsyncLoadingThread（资源异步加载）
- PhysXThreadPool（物理模拟）
- AudioThread（音频处理）

以上是UE4性能分析工具列出的线程与UE4功能的对应关系表。在UE4中，不同的线程负责不同的任务，例如GameThread负责游戏逻辑和渲染，RenderThread负责渲染和渲染资源处理，SlateThread负责UI渲染等。通过了解不同线程的功能，可以更好地分析和优化游戏性能。

UE4 PoolThread 5[0x5008] 是一个子线程。在UE4中，PoolThread通常是用于物理模拟的线程池。物理模拟是计算游戏世界中物体的运动和交互的过程，例如重力、碰撞等。在物理模拟过程中，需要大量的计算资源和内存，因此将物理模拟放在单独的线程池中可以提高游戏的性能和效率。

  

  

在UE4中，PoolThread1到15都是子线程，通常用于物理模拟。物理模拟是计算游戏世界中物体的运动和交互的过程，例如重力、碰撞等。在物理模拟过程中，需要大量的计算资源和内存，因此将物理模拟放在单独的线程池中可以提高游戏的性能和效率。

In UE4, Vorbis decompression is handled by the `FVorbisAudioInfo` class. Vorbis is a free and open-source audio codec that provides high-quality audio compression. UE4 uses Vorbis for compressing and decompressing audio files such as sound effects and music. The `FVorbisAudioInfo` class is responsible for decoding Vorbis-encoded audio data and converting it into raw PCM audio data that can be played back by the engine. If you need to decompress Vorbis audio data in your own project, you can use the `FVorbisAudioInfo` class as a reference implementation.

  

在UE4中，Vorbis解压缩由`FVorbisAudioInfo`类处理。Vorbis是一种免费且开源的音频编解码器，提供高质量的音频压缩。UE4使用Vorbis来压缩和解压缩音频文件，例如音效和音乐。`FVorbisAudioInfo`类负责解码Vorbis编码的音频数据，并将其转换为原始PCM音频数据，以便引擎播放。如果您需要在自己的项目中解压缩Vorbis音频数据，则可以使用`FVorbisAudioInfo`类作为参考实现。

  

  

Here's an example Python program that reads in the UE4 performance analysis file "ue4stats" and analyzes the thread usage times:

```Plain
import re

# Open the ue4stats file and read in the contents
with open("ue4stats", "r") as f:
    content = f.read()

# Use regular expressions to extract the thread usage times
# from the file contents
time_regex = r"\\| ([A-Za-z0-9]+) +\\| +([0-9]+\\.[0-9]+) +\\| +([0-9]+\\.[0-9]+) +\\| +([0-9]+\\.[0-9]+) +\\| +([0-9]+\\.[0-9]+) +\\| +([0-9]+\\.[0-9]+) +\\| +([0-9]+\\.[0-9]+) +\\|"
matches = re.findall(time_regex, content)

# Create a dictionary to store the thread usage times
thread_times = {}
for match in matches:
    thread_name = match[0]
    game_thread_time = float(match[1])
    render_thread_time = float(match[2])
    slate_thread_time = float(match[3])
    audio_thread_time = float(match[4])
    async_loading_thread_time = float(match[5])
    physx_thread_pool_time = float(match[6])
    task_graph_thread_time = float(match[7])
    thread_times[thread_name] = {
        "GameThread": game_thread_time,
        "RenderThread": render_thread_time,
        "SlateThread": slate_thread_time,
        "AudioThread": audio_thread_time,
        "AsyncLoadingThread": async_loading_thread_time,
        "PhysXThreadPool": physx_thread_pool_time,
        "TaskGraphThread": task_graph_thread_time
    }

# Print out the thread usage times for each thread
for thread_name in thread_times:
    print("Thread Name:", thread_name)
    print("GameThread Time:", thread_times[thread_name]["GameThread"])
    print("RenderThread Time:", thread_times[thread_name]["RenderThread"])
    print("SlateThread Time:", thread_times[thread_name]["SlateThread"])
    print("AudioThread Time:", thread_times[thread_name]["AudioThread"])
    print("AsyncLoadingThread Time:", thread_times[thread_name]["AsyncLoadingThread"])
    print("PhysXThreadPool Time:", thread_times[thread_name]["PhysXThreadPool"])
    print("TaskGraphThread Time:", thread_times[thread_name]["TaskGraphThread"])
    print()
```

This program opens the "ue4stats" file and extracts the thread usage times using regular expressions. It then creates a dictionary to store the thread usage times and prints out the usage times for each thread. You can modify this program to perform any other analysis on the UE4 performance analysis file that you need.

  

  

  

UE4中Draw Call的数量不应该超过每帧10000个，否则可能会影响游戏性能。Draw Call是指GPU绘制一个图形时发出的命令，每个Draw Call都会消耗一定的CPU和GPU资源。因此，如果Draw Call的数量过多，可能会导致游戏帧率下降，影响游戏的流畅度和体验。为了避免这种情况，可以通过优化材质、减少不必要的绘制操作、使用级联阴影等方法来减少Draw Call的数量。

CPU处理Draw Call的效率与CPU的单线程性能有关。Draw Call是GPU绘制一个图形时发出的命令，每个Draw Call都需要CPU来处理，包括计算顶点、裁剪多边形、设置材质、绘制等操作。因此，CPU的单线程性能越高，处理Draw Call的效率就越高，可以更快地将绘制命令发送给GPU，提高游戏的帧率和流畅度。除了CPU的单线程性能外，还有其他因素会影响CPU处理Draw Call的效率，例如内存带宽、缓存、调度算法等。为了最大化CPU处理Draw Call的效率，可以通过优化材质、减少不必要的绘制操作、使用级联阴影等方法来减少Draw Call的数量。

CPU单线程性能的指标单位是GHz，表示CPU的时钟速度。它越高，CPU每秒钟能够处理的指令数量就越多，处理Draw Call的效率就越高。除了时钟速度外，还有其他因素会影响CPU的单线程性能，例如指令集、缓存、调度算法等。为了提高CPU的单线程性能，可以选择高性能的CPU，优化代码，采用多线程编程等方法。

i9-9900KF是一款高端的CPU，它的单线程性能和多核性能都很强。虽然处理Draw Call的效率不仅取决于CPU的时钟速度，但是可以大致估算出i9-9900KF的处理能力。

根据我们之前提到的，UE4中Draw Call的数量不应该超过每帧10000个，否则可能会影响游戏性能。因此，如果我们假设i9-9900KF的单线程性能足够强大，那么它处理Draw Call的速率可以大约在每秒60万个左右。这只是一个估算数值，并不能代表具体的实际情况，实际处理速率还会受到其他因素的影响。

需要注意的是，这个估算数值只是针对i9-9900KF这款CPU，并不能适用于其他CPU。另外，这个数值只是一个大致估算，实际的处理速率还会受到很多其他因素的影响，例如GPU性能、内存带宽等等。因此，在实际的游戏开发中，需要进行更加详细和精确的性能测试和优化，来提高游戏的帧率和流畅度。

  

  

  

在UE4中，一个模型的Material Slot数量推荐不要超过8个。如果Material Slot的数量太多，会导致Draw Call的数量增加，影响游戏的性能。为了最大化游戏性能，应该尽量减少Material Slot的数量，并将相同的材质合并到同一个Material Slot中，以减少Draw Call的数量。

  

  

  

  

  

UE4中的Lighting GUID是一个用于标识场景的唯一ID。它通常用于在场景中共享光照数据，例如Lightmass计算的光照图。在UE4中，每个场景都有一个唯一的Lighting GUID，可以通过编辑器中的“World Settings”面板查看。如果您使用C++代码创建场景，可以使用`GetLightingScenario()`函数来获取场景的Lighting GUID。

  

  

在UE4的性能分析工具中，Render Query Result是一个与场景渲染相关的统计数据。它用于记录渲染管线中各个阶段的执行时间，例如场景剔除、光照计算、材质渲染等。通过分析Render Query Result的数据，可以确定哪些渲染阶段消耗了大量的GPU资源，从而进行优化。如果您需要更详细的信息，请参考UE4文档中有关性能分析工具和Render Query Result的内容。

在UE4中，Lighting Scenario是一个用于管理场景光照的机制。它通常用于处理场景中的动态光照，例如在游戏中更改时间、天气、季节等情况下的光照变化。每个Lighting Scenario都包含一个唯一的Lighting Scenario ID，用于标识该场景的光照信息。如果您需要在自己的项目中使用Lighting Scenario，请参考UE4文档中有关Lighting Scenario的内容。

UE4中的Lighting GUID是一个用于标识场景的唯一ID。它通常用于在场景中共享光照数据，例如Lightmass计算的光照图。在UE4中，每个场景都有一个唯一的Lighting GUID，可以通过编辑器中的“World Settings”面板查看。如果您使用C++代码创建场景，可以使用`GetLightingScenario()`函数来获取场景的Lighting GUID。

  

The UE4 Render Query Result can keep getting bigger if the scene becomes more complex, or if there are more objects to render. This can cause the GPU to work harder to render the scene, which can lead to reduced performance. To optimize performance, you may need to adjust the graphics settings or reduce the complexity of the scene. Another possible cause of a growing Render Query Result is memory leaks or other programming errors in the game code. If you suspect that this is the case, you may need to debug the code to find and fix the issue.

  

  

**UE4 RenderQueryResult是什么**

UE4 Render Query Result is a statistic related to scene rendering. It is used to record the execution time of various stages in the rendering pipeline, such as scene culling, lighting calculation, and material rendering. By analyzing the data in Render Query Result, you can determine which rendering stages consume a lot of GPU resources and optimize them. If you need more detailed information, please refer to the documentation in UE4 on performance analysis tools and Render Query Result.

优化渲染顺序可以对降低UE4 RenderQueryResult有帮助。RenderQueryResult是一个与场景渲染相关的统计数据，用于记录渲染管线中各个阶段的执行时间。渲染顺序指的是UE4渲染管线中各个阶段的执行顺序。通过优化渲染顺序，可以使渲染管线中的每个阶段更加高效地执行，从而减少RenderQueryResult所记录的执行时间。例如，可以将材质渲染阶段的执行顺序优化，使得相同类型的材质一起渲染，从而减少GPU上下文切换的次数，提高渲染效率。除了优化渲染顺序外，还可以通过其他方式来降低RenderQueryResult，例如降低场景复杂度、调整图形设置等等。

  

  

  

Occlusion Query是一种用于优化渲染性能的技术。它的原理是在渲染场景之前，先进行一些简单的计算，确定哪些物体不会对最终渲染结果产生影响，然后将这些物体从渲染队列中剔除。这样可以减少GPU的工作量，提高渲染效率。

在UE4中，可以使用Occlusion Query来剔除不可见的物体。这可以通过将物体的边界框（bounding box）与视锥体（view frustum）进行比较来实现。如果物体的边界框完全位于视锥体之外，那么该物体就可以被剔除。这样可以减少GPU的工作量，提高渲染效率。

以下是一篇关于UE4中Occlusion Query的文章链接：[Optimizing Occlusion Culling in Unreal Engine 4](https://www.gamasutra.com/blogs/RobertYang/20140826/224762/Optimizing_Occlusion_Culling_in_Unreal_Engine_4.php)

  

  

![[Untitled 1.png]]

  

  

  

  

如果UE4打包时反射和光照Build Data不正确，可能会导致渲染问题和性能问题。这通常是由于Build Data不完整或已损坏造成的。要解决此问题，可以尝试以下几种方法：

1. 确保Build Data已正确生成并保存。在打包之前，请确保已对场景进行了充分的光照计算和反射计算，并保存了Build Data。如果Build Data不完整或已损坏，可能会导致打包后的场景出现渲染问题。
2. 清除项目缓存。在UE4中，可以尝试清除项目缓存，以解决Build Data不正确的问题。在编辑器中，选择“编辑器首选项”>“清除项目缓存”，然后重新打包项目。
3. 更新UE4版本。有时，Build Data的问题可能是由UE4版本的问题引起的。尝试使用最新的UE4版本来打包项目，以确保Build Data正确生成。

如果以上方法仍无法解决问题，请考虑在UE4官方论坛或GitHub上提交问题报告，以寻求更多的帮助和支持。

  

  

  

在3D渲染中，Z-pass是一种渲染技术，用于确定哪些像素应该被渲染。它的原理是在渲染过程中，将场景中的每个像素的Z值与深度缓冲区中的Z值进行比较，如果该像素的Z值小于深度缓冲区中的Z值，那么该像素就可以被渲染。这样可以确保深度正确，避免深度冲突和渲染错误。在UE4中，可以选择使用Z-pass渲染技术来优化场景的渲染效率和质量。

在3D渲染中，Z-pass是一种渲染技术，用于确定哪些像素应该被渲染。它的原理是在渲染过程中，将场景中的每个像素的Z值与深度缓冲区中的Z值进行比较，如果该像素的Z值小于深度缓冲区中的Z值，那么该像素就可以被渲染。这样可以确保深度正确，避免深度冲突和渲染错误。在UE4中，可以选择使用Z-pass渲染技术来优化场景的渲染效率和质量。

在UE4中，可以通过在项目设置中调整渲染设置来选择使用Z-pass渲染技术。在编辑器中，选择“编辑器首选项”>“项目设置”>“渲染”，然后在“渲染设置”选项卡中选择“使用Z-pass渲染”。这样可以确保在渲染场景时使用Z-pass渲染技术，从而优化渲染效率和质量。

需要注意的是，Z-pass渲染技术并不是适用于所有渲染场景的最佳选择。在某些情况下，使用其他渲染技术可能会更加适合，例如Z-prepass、Forward Rendering等。因此，在选择渲染技术时，需要根据具体的场景需求进行选择，以达到最佳的渲染效果和性能。

  

Z-pass是一种渲染技术，用于确定哪些像素应该被渲染。它的原理是在渲染过程中，将场景中的每个像素的Z值与深度缓冲区中的Z值进行比较，如果该像素的Z值小于深度缓冲区中的Z值，那么该像素就可以被渲染。这样可以确保深度正确，避免深度冲突和渲染错误。

在渲染过程中，Z-pass通常是与其他渲染技术结合使用的。例如，在使用Deferred Rendering时，Z-pass通常用于生成深度缓冲区，从而确定哪些像素需要被光照计算。在使用SSAO时，Z-pass通常用于确定哪些像素需要被环境光遮蔽计算。

需要注意的是，虽然Z-pass可以提高渲染效率和质量，但它也有一些缺点。例如，在场景中存在大量透明对象时，Z-pass可能会导致渲染错误和深度冲突。因此，在使用Z-pass时，需要根据具体的场景需求进行选择，以达到最佳的渲染效果和性能。

  

  

  

  

  

![[Untitled 2 2.png|Untitled 2 2.png]]

生成地形时，使用质数分辨率可以避免地形高度出现明显的重复模式，从而提高地形的真实感和细节感。这是因为质数分辨率可以使地形高度图中的每个像素具有独特的高度值，从而避免了出现明显的重复模式。此外，使用质数分辨率还可以避免出现因为分辨率不够高而导致的地形高度值的不连续性，从而提高地形的平滑度和连续性。

在UE4中，可以使用高斯噪声或Perlin噪声等算法生成地形高度图。生成地形高度图时，可以选择使用质数分辨率来提高地形的真实感和细节感。如果需要更多信息，请参阅UE4文档中有关地形生成和高度图的内容。

需要注意的是，使用质数分辨率也可能会对地形生成的性能产生一定的影响。如果需要在性能和地形质量之间进行平衡，可以根据具体的场景需求进行选择。

  

更底层的原因是，使用质数分辨率可以确保每个像素的高度值都是独一无二的，这是因为质数只能被1和自身整除，因此质数分辨率可以避免出现高度值的重复。在使用非质数分辨率时，由于存在公因数，可能会导致高度值的重复出现，从而使地形出现明显的重复模式和不连续性。因此，使用质数分辨率可以避免这些问题，提高地形的真实感和细节感。

使用质数分辨率可以确保每个像素的高度值都是独一无二的，因为质数只能被1和自身整除。当使用非质数分辨率时，存在公因数可能会导致高度值的重复出现，从而使地形出现明显的模式和不连续性。因此，使用质数分辨率可以避免这些问题，提高地形的真实感和细节感。

从数学角度来看，如果假设高度值是由整数表示的，使用非质数分辨率可能会导致一些高度值与其他高度值存在公因数。例如，如果使用6的分辨率，高度值2和4具有公因数2，这意味着它们是不唯一的。另一方面，如果使用7的分辨率，这是一个质数，每个高度值都保证是独一无二的。

  

很高兴你对UE4美术地编感兴趣！以下是一些关于UE4美术地编的可能面试题：

1. 你如何在UE4中生成地形？
2. 你如何在UE4中使用高斯噪声或Perlin噪声等算法生成地形高度图？
3. 你如何使用质数分辨率来提高地形的真实感和细节感？
4. 你如何在UE4中使用蒙板来控制地形纹理的分布？
5. 你如何在UE4中处理地形的LOD？
6. 你如何使用UE4中的Landscape Editor来编辑地形？
7. 你如何在UE4中使用Spline工具来创建道路或其他线性特征？
8. 你如何在UE4中使用Foliage工具来创建植被？
9. 你如何在UE4中使用水体来模拟水面？
10. 你如何在UE4中使用雾效来增强场景氛围？

  

UE4 场景的 draw call 数量受以下因素影响：

- 渲染距离：场景中物体与摄像机之间的距离越远，渲染的物体数量就越少。可以通过调整摄像机的视野、裁剪距离、LOD、Cull Distance Volume 等方式来优化。
- 动态实例化：使用 Instanced Static Meshes 等技术可以将多个相同的物体合并为一个 draw call，从而减少渲染开销。
- 光照：场景中的光源数量和类型会影响 draw call 的数量。使用静态光照可以减少动态光照的数量，从而减少 draw call 数量。
- 材质：使用复杂的材质会增加 draw call 数量。可以通过合并材质、使用材质实例化等方式来优化。
- 物理：场景中的物理模拟也会增加 draw call 数量。可以使用物理 LOD、减少物理碰撞体数量等方式来优化。
- 粒子：大量的粒子系统也会增加 draw call 数量。可以使用粒子 LOD、粒子合并等方式来优化。
- 转换：物体的旋转、缩放、位移等变换也会增加 draw call 数量。可以使用合并网格、静态实例化等方式来优化。
- 后处理：使用大量的后处理效果也会增加 draw call 数量。可以使用后处理合并等方式来优化。

  

Niagara粒子系统是否了解和使用过？ 如何传参；

Niagara粒子系统可以通过蓝图来控制和传递参数。具体步骤如下：

1. 在Niagara编辑器中创建一个新的参数
2. 在蓝图中创建一个Niagara组件，并将其设置为你想要控制的Niagara粒子系统
3. 在蓝图中找到你想要控制的Niagara参数，并将其设置为Niagara组件的属性
4. 在蓝图中设置Niagara参数的值，这将直接影响Niagara粒子系统

需要注意的是，Niagara粒子系统的参数可以在蓝图中设置和控制，但不能直接从蓝图中读取。如果需要从蓝图中读取Niagara粒子系统的参数，需要使用Niagara蓝图库中提供的函数来实现。

例如，以下是一个使用蓝图控制Niagara粒子系统的例子：

1. 在Niagara编辑器中创建一个新的参数，例如Speed
2. 在蓝图中创建一个Niagara组件，例如MyNiagaraSystem
3. 在蓝图中找到Speed参数，并将其设置为MyNiagaraSystem组件的属性
4. 在蓝图中创建一个按键事件，并将其绑定到一个按键上，例如空格键
5. 在按键事件中设置Speed参数的值为100，这将直接影响Niagara粒子系统的速度

这样，当用户按下空格键时，Niagara粒子系统的速度将立即变为100。

需要注意的是，Niagara粒子系统的参数可以是任何类型，例如浮点数、向量、颜色等。在蓝图中控制Niagara参数时，需要根据具体的参数类型来进行设置和传递。

如果需要更多关于Niagara粒子系统的信息，请参阅UE4文档中有关Niagara的内容。

  

UE4的地形系统系是否了解和针对大型的真是地形使用过，导入地形的高程图有哪些注意事项，为什么使用质数分辨率

  

是否制作过路网模型，如果制作过是通过什么方式制作的；

  

是否了解UE4中蓝图与美术资产功能互动的基本互动方法 比如复杂的天气与天空球系统 昼夜 季节交替等等的功能实现

如果了解 举例有哪些途径

  

UE4大场景优化尝试过哪些方法， 原理是什么；

  

是否制作过可以批量使用的基于大场景优化的植被模型及其LOD模型；

  

UE4 场景的draw call都有哪些影响因素

  

模型实例数量与旋转角度 光照 材质 材质属性

  

静态模型实例的旋转角度不会增加 draw call 数量。旋转只是对模型实例的变换操作，不会创建新的网格实例，因此不会增加 draw call 数量。相反，如果在渲染过程中对模型进行缩放或位移操作，则可能会增加 draw call 数量，因为这些操作可能需要重新创建网格实例。

  

  

  

  

  

在UE4中，使用Spline工具可以轻松地创建道路或其他线性特征。但是，这些Spline Actor在打包时可能会自动转换成模型。这是因为UE4在打包时会自动将所有的Actor转换成静态网格实例，以便于优化和渲染。如果想要保留Spline Actor的动态特性，可以将其设置为Dynamic或者使用Blueprint来控制Spline的属性和行为。

需要注意的是，将Spline Actor设置为Dynamic可能会对游戏的性能产生一定的影响。如果需要在性能和质量之间进行平衡，可以根据具体的场景需求进行选择。

  

  

在UE4中，可以使用以下命令来查询加载关卡的信息：

```Plain
stat Game
```

这个命令会显示当前游戏的统计信息，包括加载时间、帧率、渲染时间等。可以通过查看这些信息来了解关卡的加载情况和性能瓶颈。

需要注意的是，这个命令只能在游戏运行时使用，不能在编辑器中使用。如果需要在编辑器中查看关卡加载信息，可以使用Editor Stats窗口来查看。可以通过选择菜单栏中的Window > Developer Tools > Editor Stats来打开这个窗口。

如果需要更多关于UE4命令和性能优化的信息，请参阅UE4文档中有关性能优化和调试的内容。

  

  

UE4的Logs文件夹包含了许多有用的信息，可以用于分析和调试游戏的问题。其中最有用的是日志文件，这些文件记录了游戏运行时发生的事件和错误。以下是一些分析UE4日志文件的常用方法：

- 打开日志文件：可以使用UE4的Log文件查看器来打开日志文件。这个工具可以将日志文件转换成易于阅读的格式，并且可以搜索、筛选、排序等。可以在UE4编辑器中选择菜单栏中的Window > Developer Tools > Log File Viewer来打开这个工具。
- 查找错误和异常：在日志文件中搜索特定的错误和异常信息，例如“Error”、“Warning”、“Fatal”等。这些信息通常会提供有用的线索，可以帮助我们找到问题的根源。
- 分析调用栈：在日志文件中搜索调用栈信息，可以了解每个函数和方法的调用顺序和参数。这些信息可以用于跟踪函数调用的路径，找到代码中的问题。
- 查看性能数据：在日志文件中搜索性能数据，例如帧率、渲染时间、物理模拟时间等。这些信息可以用于评估游戏的性能瓶颈，并且可以帮助我们优化游戏的性能。

需要注意的是，UE4日志文件包含了大量的信息，有些信息可能比较冗长和无用。因此，在分析日志文件时，需要有目的地搜索和筛选信息，以便找到有用的线索和信息。同时，需要了解UE4的日志系统和日志信息的格式，以便更好地理解和分析日志文件。

如果需要更多关于UE4日志和调试的信息，请参阅UE4文档中有关日志和调试的内容。

Log文件是UE4在运行时生成的日志文件，记录了游戏运行时的事件和错误信息。Backup Log文件是在UE4崩溃时生成的文件，用于保存崩溃时的状态和日志信息，以便于分析和调试。Backup Log文件通常包含了崩溃时的堆栈信息、寄存器信息、内存状态等，可以帮助我们了解崩溃的原因和位置。需要注意的是，Backup Log文件只有在UE4崩溃时才会生成，因此通常只用于调试和分析崩溃问题。

  

  

在UE4中，模型的面数是影响游戏性能和资源消耗的一个重要因素。模型的面数越多，需要渲染的三角形数量就越多，从而增加GPU的负担，降低游戏的帧率。同时，模型的面数也会占用更多的内存和存储空间，增加游戏的加载时间和硬盘空间消耗。

为了优化模型的面数，可以使用以下方法：

- LOD：使用LOD技术可以根据物体的远近距离来自动降低模型的面数。这样可以在远处使用简单的模型，在近处使用详细的模型，从而减少渲染开销。
- 合并网格：使用合并网格技术可以将多个相似的模型合并为一个模型，从而减少渲染开销。这个技术可以在3D建模软件中完成。
- 精简模型：使用3D建模软件可以手动精简模型的面数，从而减少渲染开销。这个方法需要一定的3D建模技能和经验。

需要注意的是，优化模型的面数不是唯一的优化方法。还需要考虑其他因素，例如光照、材质、物理模拟、粒子系统等。只有综合考虑这些因素，才能实现最优的游戏性能和资源消耗。

如果需要更多关于UE4优化的信息，请参阅UE4文档中有关优化和性能的内容。·

  

  

  

[InstalledDerivedDataBackendGraph]  
MinimumDaysToKeepFile=7  
Root=(Type=KeyLength, Length=120, Inner=AsyncPut)  
AsyncPut=(Type=AsyncPut, Inner=Hierarchy)  
Hierarchy=(Type=Hierarchical, Inner=Boot, Inner=Pak, Inner=CompressedPak, Inner=EnginePak, Inner=EnterprisePak, Inner=Local, Inner=Shared)  
Boot=(Type=Boot, Filename="%ENGINEUSERDIR%DerivedDataCache/Boot.ddc", MaxCacheSize=512)  
Local=(Type=FileSystem, ReadOnly=false, Clean=false, Flush=false, PurgeTransient=true, DeleteUnused=true, UnusedFileAge=34, FoldersToClean=-1, Path="%GAMEDIR%DerivedDataCache", EditorOverrideSetting=LocalDerivedDataCache)  
Shared=(Type=FileSystem, ReadOnly=false, Clean=false, Flush=false, DeleteUnused=true, UnusedFileAge=10, FoldersToClean=10, MaxFileChecksPerSec=1, Path=?EpicDDC, EnvPathOverride=UE-SharedDataCachePath, EditorOverrideSetting=SharedDerivedDataCache)

  

  

To view the Present time for scene rendering in UE4, you can use the following command in the console:

```Plain
stat SceneRendering
```

This will display various statistics related to scene rendering, including the time it takes to render each frame, the number of draw calls, and the number of triangles rendered. This information can be useful for optimizing the rendering performance of your game. Note that this command can only be used while the game is running, not in the editor.

"Counters Present time" is not mentioned in the document. However, to view the present time for scene rendering in UE4, you can use the following command in the console:

```Plain
stat SceneRendering
```

This will display various statistics related to scene rendering, including the time it takes to render each frame, the number of draw calls, and the number of triangles rendered. This information can be useful for optimizing the rendering performance of your game. Note that this command can only be used while the game is running, not in the editor.

  

  

UE4使用的是Deferred Rendering延迟渲染方式，它将所有的物体的信息存储在G缓冲区中，然后再进行光照计算，最后将结果合成。Deferred Rendering可以支持大量的光源和材质，但是对于透明物体和抗锯齿技术支持较差。

Unity使用的是Forward Rendering前向渲染方式，它将光照计算直接应用到每个像素上，所以可以支持透明物体和抗锯齿技术。但是对于大量的光源和材质支持较差，因为每个像素都要进行光照计算，所以渲染效率会降低。

需要根据具体的需求和场景来选择渲染方式，如果需要支持大量的光源和材质，可以选择Deferred Rendering；如果需要支持透明物体和抗锯齿技术，可以选择Forward Rendering。

如果需要更多关于UE4和Unity的渲染方式的信息，请参阅官方文档或者相关教程。

  

  

以下是UE4常用的性能分析控制台指令：

- `stat FPS`：显示游戏的帧率信息，包括平均帧率、最低帧率、最高帧率等。
- `stat UnitGraph`：显示游戏的各种性能数据，包括CPU、GPU、内存、网络等方面的数据。
- `stat SceneRendering`：显示场景渲染的性能数据，包括每帧渲染时间、绘制调用次数、三角形数量等。
- `stat Game`：显示游戏整体的性能数据，包括加载时间、帧率、渲染时间等。
- `stat StartFile`和`stat StopFile`：用于记录日志文件，可以在控制台中输入这两个指令来开始和停止记录日志。

这些指令可以帮助开发者了解游戏的性能瓶颈和优化方向，从而提高游戏的性能和质量。需要注意的是，这些指令只能在游戏运行时使用，不能在编辑器中使用。

如果需要更多关于UE4控制台指令的信息，请参阅UE4文档中有关控制台和命令的内容。

  

  

  

"Counters Present time" is not mentioned in the document. However, to view the present time for scene rendering in UE4, you can use the following command in the console:

```Plain
stat D3D11RHI
```

This will display various statistics related to scene rendering, including the present time, which is the amount of time it takes to present the rendered frame on the screen. This information can be useful for optimizing the rendering performance of your game. Note that this command can only be used while the game is running, not in the editor.

  

[[shader缓存路径]]

[[黑洞]]

[[UseGit]]

[[Blender GIS]]

[[Exposure]]

[[Niagara Learn]]

[[Runtime Virtual Texture]]

[[Brushify Landscape Material 拆解]]

[[Editor Utility Widget]]

[[UE5.3 Tessellation]]

[[UE 透明材质的理解和应用]]