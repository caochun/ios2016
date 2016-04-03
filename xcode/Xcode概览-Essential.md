title: Xcode 精髓
date: 2015-10-07 18:10:47
category: xcode概述
tags:
---
Xcode 概述
<!--more-->

## Xcode 精髓（[Xcode Essentials](https://developer.apple.com/library/ios/documentation/ToolsLanguages/Conceptual/Xcode_Overview/index.html#//apple_ref/doc/uid/TP40010215-CH24-SW1]))

***

### 概览 [(At a Glance)](https://developer.apple.com/library/ios/documentation/ToolsLanguages/Conceptual/Xcode_Overview/index.html#//apple_ref/doc/uid/TP40010215-CH24-SW1)
***
[Xcode](https://developer.apple.com/library/ios/documentation/ToolsLanguages/Conceptual/Xcode_Overview/index.html#//apple_ref/doc/uid/TP40010215-CH24-SW1)
是苹果的集成开发环境(IDE),开发者可用于开发适用于苹果iPad、iPhone、iWatch以及Mac设备上的应用程序。在应用程序的创建、测试、优化以及提交至App Store的过程中，Xcode为开发者提供了用于管理整个开发工作流的工具。


### 单窗口界面（[Single-Window interface](https://developer.apple.com/library/ios/documentation/ToolsLanguages/Conceptual/Xcode_Overview/index.html#//apple_ref/doc/uid/TP40010215-CH24-SW1)）
***
Xcode界面在单工作区窗口集成了代码编辑、用户界面（UI）设计、资产管理、测试以及调试等版块，这些窗口会根据开发者的工作重新配置内容。比如在某个区域选中一个文件，相应的编辑器会在另一个区域被打开。选中一个符号或者UI对象，那么其文档将会出现在紧邻的面板中。

您可以仅展示所需内容来专注于某项任务，比如仅展示源码或UI布局，或者你可以同时进行编码和UI布局。你可以打开多个窗口或者在每个窗口上打开多个Tab来进一步自定义环境。

![1.png](/images/xcode1.png)


### 辅助代码编辑 [Assisted Source Code Editing](https://developer.apple.com/library/ios/documentation/ToolsLanguages/Conceptual/Xcode_Overview/index.html#//apple_ref/doc/uid/TP40010215-CH24-SW1)
***

无论您使用Objective-C, Swift, C, C++，或者是混合使用这些语言，Xcode都会在输入时即时进行检测。当Xcode发现到一个错误时，源码编辑器会对错误进行高亮显示，并提供修复。Xcode可通过智能补全功能来加快您的输入，可使用现成的代码片段或者源文件模板来进一步减少你的输入。在Swift中，Playgrounds可让你无需构建和运行应用程序即可进行交互式的编码体验。

您可以简单地配置源码编辑器来展示同一文件的多个视图，或者一次查看多个相关文件。搜索、替代和重构操作可帮您快速安全地对代码进行大量修改。通过各种各样的功能，Xcode让您编写高质量代码变得前所未有的简单。

![2](/images/xcode2.png)


### 图形用户界面设计 [Graphical UI Design](https://developer.apple.com/library/ios/documentation/ToolsLanguages/Conceptual/Xcode_Overview/index.html#//apple_ref/doc/uid/TP40010215-CH24-SW1)
***
Interface Builder（IB） 是一款集成在Xcode中的可视化设计编辑器。开发者可使用IB组合窗口、界面、控件、菜单以及其他元素（可配置对象库或者或你创建的库中的元素），从而构建iOS或者Mac app的用户界面。开发者可使用Storyboards来指定应用程序的flow，以及界面间的过渡，然后根据执行代码图形化地连接对象和过渡。

![3.png](/images/xcode3.png)

使用Xcode的Auto Layout特性为项目定义约束，以便其能根据屏幕尺寸、窗口尺寸以及本地化自动调整。使用Size Classes为任何屏幕尺寸组合和方向调整您的移动UI：自定义Auto Layout约束，添加或者移除是视图，甚至是改变字体。

![4.png](/images/xcode4.png)

Xcode中的资产目录可帮您管理在app中使用的图片文件和数据文件。图片文件比如icon、自定义美术作品以及启动图片等。

![5.png](/images/xcode5.png)

通过Xcode的粒子发射器，您可以通过添加动画效果来提高iOS或Mac游戏的水平，比如雪花、火花以及烟雾。对于Mac 应用程序来说，SceneKit编辑器可帮您使用3D创作工具创建的场景，并将其作为数字资产交换（DAE）文件输出。

![6.png](/images/xcode6.png)

### 集成调试 [Integrated Debugging](https://developer.apple.com/library/ios/documentation/ToolsLanguages/Conceptual/Xcode_Overview/index.html#//apple_ref/doc/uid/TP40010215-CH24-SW1)
***
当Xcode在调试模式中启动应用程序时，它会立即开启调试会话。如果您运行的是一款iOS 或者watchOs app，那么Xcode将在iOS模拟器或者连接至Mac的设备上启用它。如果您运行的是一款Mac app，那么Xcode将直接在您的Mac上打开它。

![7.png](/images/xcode7.png)

您可以直接在源码编辑器中调试应用程序。通过在变量名称上移动鼠标来查看对象的内容，然后使用Quick Look来检测某个特殊值。调试区和调试导航器可让您在检查代码的时候谨慎地控制应用程序的执行。对于更加精细的控制，控制台会提供命令行来访问调试器。

![8.png](/images/xcode8.png)

调试仪表板会展示应用程序的资源消耗情况，以帮您在用户发现问题之前确定其所在。

![9.png](/images/xcode9.png)


### 测试和持续集成 [Testing and Continuous Integrations](https://developer.apple.com/library/ios/documentation/ToolsLanguages/Conceptual/Xcode_Overview/index.html#//apple_ref/doc/uid/TP40010215-CH24-SW1)
***

为了帮您开发一款高质量的应用程序，Xcode包含了可用于功能、性能和用户界面测试的测试框架。您可以编写测试用例并使用测试导航器来运行测试并查看测试结果。你可以进行单元测试来查看当前代码片段。性能测试可确保app的重要部分不会让用户等待。为定期运行测试设置触发器，以便您能捕捉代码和性能中的回归缺陷（regression bugs）。

在测试导航器中中运行您的测试，查看测试结果，并作任何所需的更改来通过测试。您可以使用Xcode service来自动执行测试。你可以创建运行在单独服务器上 bots 来定期执行单元测试，或者是每次提交源码时执行任务。

![10.png](/images/xcode10.png)

除了运行单元测试外，bots会基于代码自动执行静态分析，构建您的应用程序，并归档项目用于分发给测试者或者提交至App Store。虽然可执行app的这些持续集成，但是bots也会报告编译错误、警告、静态分析器问题以及失败的单元测试。


### 自动保存、工程快照以及源码控制管理 [Automatic Saves and Source Control Management](https://developer.apple.com/library/ios/documentation/ToolsLanguages/Conceptual/Xcode_Overview/index.html#//apple_ref/doc/uid/TP40010215-CH24-SW1)
***

工作过程中，Xcode会自动保存您对源码和项目文件所做的更改。该功能无需配置，因为Xcode会持续跟踪您的更改并保存它们，您可以通过Undo和Revert Document命令将文件恢复至先前的状态。

想要更精确地跟踪所做的变化，可使用Xcode的源码控制功能。Xcode支持两种流行的源码控制系统：Git和Subversion。您可以访问远程Git和Subversion源码仓库，并创建本地Git仓库。通过适用于OS X Server 的Xcode service，您可以将Git仓库托管在自己的服务器上。

![11.png](/images/xcode11.png)


### 完善的文档 [Integrated Documentation](https://developer.apple.com/library/ios/documentation/ToolsLanguages/Conceptual/Xcode_Overview/index.html#//apple_ref/doc/uid/TP40010215-CH24-SW1)
***

当您编码时，Xcode可为您提供详细的技术信息。根据需要，Quick Help可在视图内为您提供简明的API信息。通过一步步指示来执行常规的Xcode任务，你会发现Xcode帮助信息俯拾皆是。

Xcode包含大量使用方面的文档，并且提供了全面的SDK文档，包括编程指南、教程、示例代码、详细的框架API参考以及苹果工程师的演示视频。所有这些资源可在Xcode文档查看器中找到，并且可通过后台自动下载来更新文档。



### 将应用程序分发给测试者或者提交App商店 [App Distribution to Testers and App Store](https://developer.apple.com/library/ios/documentation/ToolsLanguages/Conceptual/Xcode_Overview/index.html#//apple_ref/doc/uid/TP40010215-CH24-SW1)
***

您的大部分开发时间都花在编码任务上，但是针对App Store进行开发，您需要在app的生命周期内执行一系列的管理任务。除了Xcode，您还需要使用Member Center 来管理开发者计划账户和权益，您也将会使用iTunes Connect 检查合同的状态、设置税金和银行信息，获得营收和财务报告，并管理app的元数据。

Xcode项目配置有助于将您的应用程序分发给测试者和提交至App Store。提交至App Store是一个多步过程，从您签署 iTunes Connect和提供必要的产品信息开始。在Xcode中，您需要创建项目的档案并提交至商店。当应用程序通过审核后，您可以使用iTunes Connect设置发布日期。（如果您在商店之外分发Mac app，您需要遵守一个略有不同的进程步骤）
