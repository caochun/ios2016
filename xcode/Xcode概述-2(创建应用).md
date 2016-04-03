title: Xcode 创建应用
date: 2015-10-05 18:26:47
category: xcode概述
tags:
---
Xcode 概述
<!--more-->

## 创建应用Creating Apps
***

### 管理工程 [Working with Projects](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/CreatingProjects.html#//apple_ref/doc/uid/TP40010215-CH31-SW1)
***
在Xcode中创建的应用程序需要一个“project（项目）”来组织必需的文件和资源。您可以通过选择 File > New > New Project 来创建一个新的项目。Xcode将会打开一个新的工作区窗口并显示一个对话框，来让您选择一个合适的项目模板。Xcode为iOS和Mac应用程序开发提供了许多常见样式的内置模板。这些模板包含了必要的项目配置和文件，以帮助您快速启动开发工作。

![xcode2_1](/images/xcode2_1.png)

您可以在项目导航栏查看项目文件的名称。当您在项目导航栏选中了一个文件，该文件的内容将会显示在合适的编辑器或查看器中。下方的屏幕截图展示了Adventure项目。在项目导航栏中选中一个实现文件（APAViewController.m），该文件内容则显示在源码编辑器中。

![xcode2_2](/images/xcode2_2.png)


#### 项目中存放着搭建应用程序所需的文件和资源([A Project Is a Repository of Files and Resources for Building Apps](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/CreatingProjects.html#//apple_ref/doc/uid/TP40010215-CH31-SW1))
***
项目包含了搭建一个或多个应用（或者其他软件产品，例如命令行工具以及插件）所需的元素。项目同样还维护着这些元素之间的关系。这些元素包括了：

* 源代码文件（包括相应的实现文件和头文件）、库和框架、图片文件和用户界面文件。
* 在项目导航器中负责组织文件架构的组文件夹（Groups）。
* 项目级别的应用编译配置。
* 产生单个应用的对象（Targets）。

选中项目导航器中的项目名称，则打开项目编辑器。您可以使用编辑器来确定如何编译应用程序，从SDK版本到指定编译器选项。在这张截图中，我们选中了项目导航器中的Adventure项目并打开了项目编辑器，项目编辑器展示了Adventure项目的信息面板。

![xcode2_3](/images/xcode2_3.png)

创建项目后，Xcode会提供两个标准项目级的编译配置：调试和发布。这些配置的不同之处主要在于它们是否包含调试信息，以及版本优化程度。这两项编译默认配置应该足以满足您的产品开发需求。一般情况下，开发者不必更改编译设置。

要添加更多的编译配置项，可打开项目编辑器，复制项目现有配置中的某项配置，然后修改它的设置。例如，您可以配置一个包含调试信息的全面优化编译设置，以便于调试优化代码。

![xcode2_4](/images/xcode2_4.png)

#### 打开关闭工程或者工作区([Closing and Opening a Project or a Workspace](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/CreatingProjects.html#//apple_ref/doc/uid/TP40010215-CH31-SW1))

要关闭一个项目或工作区，选择 File > Close Project or File > Close Workspace 。Xcode将会记住您曾经打开过的窗口以及它们的配置情况，当你重新打开项目或工作区后则恢复这些配置。

### 管理对象 [Working with Targets](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/WorkingwithTargets.html#//apple_ref/doc/uid/TP40010215-CH32-SW1)

每个项目都至少包含一个对象（target）。一个target可指定构建的产品，比如是一个iOS或Mac应用。在项目编辑器中选中一个target来查看和修改其设置。在下面的截图中，Adventure项目的Adventure iOS target在项目编辑器中被选中。该项目编辑器显示了该对象的General面板。

![xcode2_5](/images/xcode2_5.png)

对象的General面板显示了一些您偶尔会检查并可能修改的基本设置。在应用开发过程中，您通常在其他地方修改这些值，比如说，在创建一个新项目时出现的对话框中设置。

对于iOS应用来说，General面板中包含的对象设置有：

* bundle Identifier：包标识符，这是一个让操作系统和App Store识别应用的字符串。
* Version : 发布应用程序的版本号。
* Build：内部版本号，它标识了应用程序的某个特定版本。
* Team：加入了苹果开发者计划的开发团队的名称。
* Deployment Target：即应用最低能够运行的iOS版本。
* Devices：能够运行应用的设备
* Main Interface：应用启动时预加载的主用户界面。
* Devices Orientation：应用程序支持的用户界面方向（纵向，上下颠倒，横向左置，横向右置）

对于watchOs应用，General面板中包含的对象设置有：

* 应用名称
* 包标识符
* 版本号
* 内部版本号
* app图标


对于Mac应用来说，General面板中包含的对象设置有：

* 应用类别，用来在Mac App Store中应用分类
* 包标识符
* 版本号
* 内部版本号
* 可选值，内容要么是Mac App Store中的签名代码，或者是在Mac App Store外分发的某个开发者ID的签名代码，或者是未签名符号。
* 部署对象，即应用最低能够运行的OS X版本
* OS X中用来让用户识别应用程序的icon

有关调试或发布应用的具体信息，请参阅Run Your App.

#### 向对象中加入苹果提供的技术 *Adding Technology Features to a Target*
***
要向应用中添加各种各样的苹果技术，比如说iCloud、游戏中心、应用内购买以及地图等等，那需要在项目编辑器中选中对象，然后单击Capabilities选项。通过打开功能的开关来向应用中添加功能。Xcode将会向您的项目中添加必要的权益（entitlements）文件，并将必要的框架链接到target上。在某些情况下，Xcode中可能会碰到激活功能失败方面的问题。如果碰到此类问题的话，出错信息将被显示在该功能中的信息区域中。

您可以通过单击功能名称左边的三角形按钮来显示或隐藏功能细节。当功能未激活时，该区域大致描述了该功能和激活该功能时的操作。当功能激活时，可使用该区域查看或更新相关的配置，并鉴定需要修复的
问题。

![xcode2_6](/images/xcode2_6.png)

有关添加功能的更多信息，请参见App Distribution Guide中Adding Capabilities一节。

#### 向对象中添加文件类型和服务信息  (*Adding File Type and Service Information to a Target*)
***
对象的Info面板显示了和应用程序相关的属性，以及应用程序能够创建或打开的文件类型，并且对于OS X来说，还显示了应用程序所能提供的服务。绝大多数的自定义对象属性可在Xcode界面的其他部分进行修改（比如说在General面板中设置的包标识符、版本号以及内部版本号）。下面的截图显示了Adventure应用iOS对象的Info面板。

![xcode2_7](/images/xcode2_7.png)

文档类型设置指定了能够在应用中创建和编辑的文档类型，并且提供了可在iOS或Mac OS中展示的代表该文档类型的自定义图标。

您可以为应用程序添加输出和导入UTI（统一类型标识符）来让其能够导入或者输出任何文件类型。和专用于应用程序的文档类型不同，UTI指定了某些通用的格式，比如说纯文本或者.png。举个例子，UTI支持在应用间使用剪贴板复制和粘贴。想获得关于支持类型列表的相关信息，请参见Uniform Type Identifiers Reference.

URL类型设置允许您通过使用自定义协议为应用间交换的数据指定自定义schemas。例如一些现有的schemas，比如HTTP、mailto以及SMS。欲了解更多信息，请参阅App Programming Guide for iOS (iOS)中的Using URL Schemes to Communicate with App一节，或者参阅Launch Services Programming Guide(Mac OS)。

Mac OS应用使用出现在Services菜单上的Services项目来添加新的项目。欲了解更多信息，请参阅“Services Implementation Guide”。

#### 给对象重写编译设置 (*Overriding Build Settings for a Target*)
***
对象中包含了编译应用的指令——以编译设置和编译阶段的形式。target继承了项目的编译设置。虽然绝大多数开发者很少需要更改这些设置，但是您仍然可以通过在对象层面确定不同的设置项来重写项目的所有编译设置。在项目编辑器中选中一个对象，然后在Info、Build Settings或者Build Phases面板中修改项目设置。



### 使用工作区来处理关联项目 [Working on Realated Projects](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/WorkingonRelatedProjects.html#//apple_ref/doc/uid/TP40010215-CH33-SW1)
***
工作区是项目的集合，它可以降低大型应用程序的复杂性。工作区具有以下几个优点：

工作区的所有项目都可以访问同一工作区的其他项目，包括编译信息。
您可以设置项目之间的依赖关系，这样一个简单的编译命令就可以编译所有选中对象所需的片段。
您可以将静态库或模块包含进工作区，无论是您自己的还是第三方的。
您可以将大项目分解成更小的项目，使功能维护和共享更加方便。
通过选择 File > New > Workspace 来创建一个工作区。当创建一个工作区后，您可以在其中创建新项目，并且可以向其中添加现有项目。在创建工作区后，请打开工作区文件，而不是打开项目文件。

现有的项目转换成工作区请选择 File > Save As Workspace 。该项目的当前窗口将被转换到工作区窗口。

以下屏幕截图显示了包含两个Xcode项目文件的工作区示例。导航区最上方的那个项目是一个名为MySharedFramework的框架。另外一个项目文件是一个应用程序，名为UsesSharedFramework，其中包含了共享的框架。使用工作区可以让应用项目能够访问共享的框架中的所有文件，同时也让诸如调试之类的任务更加轻松。添加该框架到应用程序为应用程序和框架之间创建了一种依赖关系。Xcode在应用编译之前检查框架是否需要编译。

![xcode2_8](/images/xcode2_8.png)
