title: Xcode 添加资源
date: 2015-10-02 18:26:47
category: xcode概述
tags:
---
Xcode 概述
<!--more-->

## 添加资源 [Adding Assets](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/AddingImages.html#//apple_ref/doc/uid/TP40010215-CH50-SW1)
***

### 添加图像 [Adding Images](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/AddingImages.html#//apple_ref/doc/uid/TP40010215-CH50-SW1)
***

为了更好地帮助您创建应用以及管理用户界面元素，除了Interface Builder之外，XCode 还提供了其他的工具来达成这个目的。

您可能会为应用添加许多图像，包括为不同的iOS设备准备的图标、自定义图片以及启动界面。其中一些图片向 App Store 提交时需要的。Asset catalog（资源目录）可以帮你很好地管理这些内容。

![xcode5_1](/images/xcode5_1.png)

借助粒子发射编辑器，您可以通过添加诸如雪花、火花和烟雾等可移动粒子在内的动画效果来增强您的应用程序。这些特效对于 iOS 和 Mac 上的游戏来说特别有用。

![xcode5_2](/images/xcode5_2.png)

#### 添加应用图标和启动界面 *Adding App Icons and Launch Image*
***

您需要为您应用所支持的所有操作系统版本和设备添加相应的应用图标。iOS 应用和 Mac 应用所需的图标种类不同。对于这两个平台来说，请在 Xcode 中的 asset catalog 中添加应用图标所需的版本。

对于 iOS 应用程序来说，所添加的应用图标将显示在设备的主屏幕和 App Store 上。Xcode 没有提供能创建图标的图形制作工具，请使用专门的设计软件来进行制作。请创建出一些在不同场景下使用的图标。您的 iOS 应用包含一个小图标（当显示搜索结果时使用）和一个高分辨率图标（用在有 Retina 显示屏的设备上）。如果您的 iOS 应用部署目标是通用的话，您还可以创建适用于 iPad 和 iPhone 设备上的图标版本。

对于 Mac 应用程序来说，创建一组图标集，包括为每个图标大小创建的图标对（标准和高分辨率）。以像素为单位就是：16 x 16, 32 x 32, 128 x 128, 256 x 256, 以及512 x 512。Finder 将使用这些图标来向用户显示您的应用

#### 使用Asset Catalog 中的图片资产 *Work with Image Assets in the Asset Catalog*
***

当您创建完新的项目之后，Xcode 将会创建一个名为`Images.xcassets`的资产目录。在项目导航栏中选中asset Catalog，然后 Xcode 就会在编辑区打开它。

Asset catalog 包含了一个图片集列表。每一个图片集（比如说截图中的 AppIcon）都包含了所有的图片版本，以支持不同的设备和分辨率。您可以通过将图标拖曳进合适的图标格子中，来向您的应用中添加图标。

![xcode5_3](/images/xcode5_3.png)

您可以在应用中为诸如按钮或者其他控件创建额外的图片集。要创建一个空图片集或者要向新图片集中导入图片，请单击位于图片集列表底部的 Add 按钮（+）。

#### 创建并设置 iOS 启动界面（或者启动界面文件） *Create and Set the iOS Launch Screen File*

***

当您在 iOS 上启动您的应用时，启动界面会首先显示出来。启动界面会在用户单击应用图标之后即刻显现，然后它会一直停留，直到您的主界面显示出来。如果您的应用在 iOS 8 或者更高版本运行，系统将采用一个 xib文件作为启动界面，并且根据屏幕大小来显示合适的尺寸。如果是要在 iOS 8 之前的版本进行开发，那么您就必须要向 asset catalog 中添加一系列的启动图片，以适应所有可能的屏幕尺寸。

新项目创建的时候会同时创建一个启动界面文件，名为`LaunchScreen.xib`。您也可以自行创建启动界面文件，选择 File > New，然后选中 User Interface category，接下来选择 Launch Screen 这个文件类型。启动界面文件使用 size classes 来适应不同屏幕尺寸和方向。

由于启动界面是在您应用运行前显示的，因此您只能使用 UIView 或 UIViewController 类型的唯一根视图。您同样也只能使用不需要更新的 UIKit 类。

要设置启动界面，请打开编译对象的 General 信息栏，然后从弹出菜单中选择启动界面文件。


#### 为 iOS 7 以及更早版本创建并设置iOS启动图片 *Create and Set iOS Launch Images for iOS 7 and Earlier*
***

您可以在一个设备上轻易地捕捉到启动图片的截图。您可以在设备上配置好您想要屏幕显示的方式，然后同时按下设备的锁定键以及 Home 键。然后您的截图就被保存在照片应用中的相机胶卷中。将这个截图从您的设备中拷贝到 Mac 上。比如说您可以使用 iPhoto 应用来完成这个操作，将屏幕截图从设备中导入，然后在以 PNG 格式导出到 Mac 上。

要将该截图设置为启动图片，选择项目导航栏中的 asset catalog 文件，然后选择 LaunchImage 图片集。将您的截图拖曳到合适的单元格中。

### 添加例子发射特效 [Adding Particle Emitter Effects](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/AddingParticleEmitterEffects.html#//apple_ref/doc/uid/TP40010215-CH51-SW1)

***

Sprite Kit 提供了渲染图形和动画的基础设备，这个功能对 iOS 和 Mac 的游戏开发者来说特别有用。这种基础设置包括了粒子发射器。粒子发射器可以轻松制作小到一个几乎不动的粒子，大到成千上万个在屏幕上飞舞的小颗粒。您可以使用它来模拟火、雨、烟雾、雪花、火焰等动画效果。

XCode 提供了8个粒子发射器模板和一个用来操纵粒子外观和行为的编辑器。

在 Xcode 中使用 New Project 模板来创建一个 基于 Sprite Kit 的游戏，或者使用在项目编辑器中的General 窗格来向一个已存在的编译对象中添加 Sprite Kit 框架。要向您的项目中添加一个粒子发射器，请选择 File > New > File，然后选择 Resource > SpriteKit Particle File。

![xcode5_4](/images/xcode5_4.png)

然后从下拉菜单中选择例子发射器模板，单击下一步，在 Save As 区域中输入发射器的名称。接着选择在编译对象去中的和您项目相关的复选框。Xcode 将会创建一个带有.sks后缀的文件。

在项目导航器中选中您的粒子发射器文件，然后 Xcode 将会在粒子发射编辑器中打开这个文件。

![xcode5_5](/images/xcode5_5.png)

使用粒子发射检查器（ParticleEmitterInspector）来修改和检查粒子的效果。例如，您可以更改创建粒子的速度，粒子的样式，以及例子在创建后的行为。对检查器中所做的更改将立即生效，并可以在编辑器中查看。

### 向Mac应用中添加3D场景 [Adding 3D Scenes](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/Adding3DScenes.html#//apple_ref/doc/uid/TP40010215-CH52-SW1)

SceneKit 是为 Mac 应用准备的 3D 渲染框架。Sprite Kit 支持导入、处理和渲染 3D 项目，而不需要您拥有丰富的 3D 图形编程技能。借助 Scene Kit 编辑器，您可以预览 3D 场景，检查您源代码中需要的信息，以及调整场景对象的参数，以为您的应用加强和微调渲染效果。

要向项目中导入数字资源交换(digital asset exchange, DAE)文件，请使用项目导航栏。选择一个您想保存该文件的文件夹，然后选择 File > Add Files，然后选择该文件单击 Add。要在 Xcode 中浏览 3D 场景，在项目导航栏中选择这个 DAE 文件。Xcode 将在 Scene Kit 编辑器中打开这个文件。

要预览该场景并运行动画，使用 Scene Kit 编辑器主区中控制命令。按下 Play 按钮来播放动画，按下 Pause 按钮来暂停动画，然后滑动滑动条来滚动这个动画。使用触控板或者鼠标来操作这几点。

在工具区的检查器允许您查看并编辑位于场景图像列表或示例对象的节点信息。例如，借助与检查器相关的节点，您可以调整相机、光线或者集合属性，同样借助资源检查器，您可以调整资源上的许多设置和属性，比如说为其选择一个照明模型和一个内容文本。

![xcode5_6](/images/xcode5_6.png)

### 向Mac应用中添加数据文件 [Adding Data Sets](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/AddingDataSets.html#//apple_ref/doc/uid/TP40010215-CH72-SW1)

***
![xcode5_7](/images/xcode5_7.png)

### 向Mac应用中添加[Watch Complications](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/AddingWatchComplications.html#//apple_ref/doc/uid/TP40010215-CH73-SW1)

![xcode5_8](/images/xcode5_8.png)
