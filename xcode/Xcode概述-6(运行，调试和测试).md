title: Xcode 运行、调试和测试
date: 2015-10-01 18:26:47
category: xcode概述
tags:
---
Xcode 概述
<!--more-->


## 运行您的应用 [Running Your App](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/BuildingYourApp.html#//apple_ref/doc/uid/TP40010215-CH53-SW1)
***

### 生成您的应用 [Building Your App](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/BuildingYourApp.html#//apple_ref/doc/uid/TP40010215-CH53-SW1)
***
要编译并运行您的 iOS 或 Mac 应用，请在工作区的工具栏上选择一个编译方案，然后选择运行目标，接着单击 Run 按钮。单击 Stop 按钮即可使应用退出。

![xcode6_1](/images/xcode6_1.png)

如果您要运行 iOS 应用，Xcode 便会通过 iOS 模拟器或者是连接到 Mac 的 iOS 设备来启动它。而如果您要运行 Mac 应用的话，Xcode 会直接在 Mac 上运行它。

#### 选择一个Scheme来生成应用 *Choosing a Scheme to Build Your App*

编译方案(scheme)是一系列设置的集合，它指定构建项目的对象、所使用的编译配置，以及当应用启动时需要的运行环境。当您打开一个现有项目（或者创建一个新的项目）时，Xcode 将会自行为每个对象创建一个编译方案。默认的编译方案名称和您项目的名称相同，并且包含了五个运行操作的设置项：

* 运行应用
* 针对对象的运行单元测试
* 描述应用的性能特性的简介
* 为代码执行静态分析
* 归档应用应用为分发做准备，比如说分发给测试者或者上传到 App Store

每项操作都能生成应用，并将其作为可执行项目来运行。要选择编译方案，请使用在 Xcode 工作区工具栏上的Scheme menu。（您可以同样使用编译方案菜单来选择运行目标。）

#### 选择一个目标来运行应用 *Choosing a Destination to Run Your App*
****
当您生成应用的时候，运行目标（destination）将决定当应用生成完毕后其在何处运行。对于 Mac 应用来说，运行目标就是生成应用的这台 Mac 电脑。对于 iOS 应用来说，运行目标可以是连接至 Mac 的已配对 iOS 设备，也可以是 iOS 模拟器。iOS 模拟器和 iOS SDK 一起伴随着 Xcode 安装到您的 Mac 上，它可以在 Mac 上运行，并且可以模拟 iPhone 或者 iPad 的运行环境。

![xcode6_2](/images/xcode6_2.png)

Scheme菜单可以让您自由组合编译方案和运行目标，但是这两个设置是截然不同的。编译方案和运行目标并没有从属关系。在上述的截图当中，编译方案是 Adbenture iOS，运行目标是 iPhone Retina (4-inch) 模拟环境。其结果是 Adventure iOS 编译方案生成一个在模拟的 iOS 设备上运行的 iOS 程序。如下图所示，同一个编译方案可以在不同的运行目标上运行，比如说在模拟的 iPad 或在真机上运行。

![xcode6_3](/images/xcode6_3.png)

### 在模拟器中运行 [Running in the Simulator](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/RunningintheSimulator.html#//apple_ref/doc/uid/TP40010215-CH54-SW1)
***

iOS 模拟器允许您模拟一系列的 iPhone 和 iPad 设备，也可以模拟不同版本的 iOS 操作系统。您可以用键盘以及触控板来与 iOS 模拟器交互，来模拟单击、设备旋转，以及其他操作。例如，您可以使用 iOS 模拟器中的 Hardware 菜单来：

* 向左或向右旋转模拟器
* 模拟用户摇动设备
* 给前台应用发送一个模拟的内存不足警告

作为在真机测试前的初始工具，iOS 模拟器是您在整个开发流程中测试应用原型好工具之一。虽然您可以在 iOS 模拟器中测试您应用的基本操作，但是 iOS 模拟器作为一个测试平台仍然是有许多限制。在开发应用的过程中，真机测试是必不可少的。

![xcode6_4](/images/xcode6_4.png)

#### 创建自定义模拟器配置 *Create Custom Simulator Configurations*
***
选择 Window > Devices 来打开设备管理器。单击管理器窗口左下角的添加按钮（+）。在出现的对话框中，输入您自定义模拟器配置的名称，然后选择一个 iOS 版本。单击 Create ，这样您的自定义模拟器配置就被添加到模拟器列表中了。默认情况下，新的配置出现在运行目的目标菜单中。

![xcode6_5](/images/xcode6_5.png)

#### 在运行目标菜单中显示模拟器或真机 *Show Simulators or Devices in the Run Destinations Menu*
***
选择 Window > Devices。在设备管理器中，选择您想要在对象菜单中添加或者移除的设备。然后选择管理器窗口左下方的配置按钮选择 Show in Run Destinations Menu。旁边的复选标记将表明该设备或者模拟器是否会显示在运行目标菜单中。

![xcode6_6](/images/xcode6_6.png)

### [Running on a Device](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/RunningonaDevice.html#//apple_ref/doc/uid/TP40010215-CH55-SW1)
***
Xcode 在您的开发 Mac 环境上启动 Mac 应用。

![xcode6_7](/images/xcode6_7.png)


开发过程中，要在真机（iPad、iPhone或者 iPod touch）上运行 iOS 应用，需要如下四个条件：

设备需要连接至 Mac
您是苹果开发者项目的成员
您拥有一个开发者项目的有效签名证书
设备被开发者项目使用，且已被配置为可开发
如果您有条件没有满足，那么 Xcode 将会引领您进行修复，并且通常可以添加签名身份以及设备配置文件。

开发过程中，要在真机（iPad、iPhone或者 iPod touch）上运行 iOS 应用，设备必须连接到 Mac，并且该设备必须被苹果认证为可开发。如果您的 Mac 应用使用特定的 App 技术--如 iCloud，Game Center以及 In-App Purchase，那么您的 Mac 必须被认证。

苹果实现了一个基本的安全模型来保护用户数据，并且保护您的应用程序以防其在不知情的情况下被修改或被分发。在整个开发过程当中，您将创建资产（assets）并输入信息，让苹果用来验证识别您身份、您的设备以及您的应用。这些资产包括配置文件，用来确定您的开发设备。

要获得一个设备的配置文件，您需要成为苹果开发者计划的成员并且获得相应的签名身份。

#### 为运行目标选择设备 *Choosing Your Device for the Run Destination*
***


### 编辑、创建以及管理编译方案 [Managing Schemes](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/ManagingSchemes.html#//apple_ref/doc/uid/TP40010215-CH56-SW1)
***

要编辑编译方案，在编译方案菜单中选择 Edit Scheme。编译方案配置对话框的左边栏列出了编译方案能够执行的操作。您可以修改每个操作的设置。在截图中，Run 操作被修改为在 Xcode 运行应用时模拟 Mexico City 这个地点。

![xcode6_8](/images/xcode6_8.png)

您可以修改编译方案以让其执行下述操作：

* 生成多个目标
* 在某个操作执行前或执行后运行某个脚本
* 在某个操作执行前或执行后发送邮件
* 使用内存管理诊断来运行应用
* 为某个操作设置为调试(debug)或发布(release)，例如下面这个截图所示的 Run 操作。

创建新的编译方案的最便捷方式是单击编译方案复制按钮，这个按钮使用可用的编译方案作为模板来让您可以重命名、编辑以及保存一个新的编译方案。如果您创建了一个编译方案，就可以通过单击位于编译方案配置对话框中的管理方案按钮。或者如下面截图所示的通过选择编译方案菜单中的 Manage Schemes。您可以重命名编译方案，也可以重新组织其在编译方案菜单中显示的方式。您也同样可以指定该编译方案是否可以在菜单中显示，指定该编译方案应该被存储在项目或者是工作区的何种位置，以及指定该编译方案是否可以被共享，比如说团队成员从源代码库中访问项目。您可以单击 Autocreate Schemes Now 按钮来让 Xcode为没有编译方案的对象自行创建编译方案。


![xcode6_9](/images/xcode6_9.png)

## 调试 [Debugging](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/UsingtheDebugger.html#//apple_ref/doc/uid/TP40010215-CH57-SW1)

***
### 使用 Debugger [Using the Debugger](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/UsingtheDebugger.html#//apple_ref/doc/uid/TP40010215-CH57-SW1)
***
当您点击了工作区工具条中的运行按钮并且你的应用编译成功，那么Xcode运行您的应用程序并开启调试功能。您可以使用图形化的工具直接在源码编辑器中调试应用，比如使用Data tips、快速查看(Quick look)来查看变量值。

调试区域(Debug area)和调试导航器(Debug navigator)可以让您检查运行中的app的状态，并控制其执行。

![xcode7_1](/images/xcode7_1.png)

为了创建一个高质量的应用，要尽可能减少应用对用户系统的影响。使用调试导航器（Debug navigator）中的调试仪表（Debug gauges）深入了解你应用的资源消耗，当你发现问题时，请使用Instruments确认并分析应用的性能。

如果你正在开发一款iOS应用，在设计和早期测试阶段可以使用iOS模拟器找出存在的问题。

你可以配置Xcode来帮助你专注于调试任务。举例来说，当代码运行到一个断点时，你可以让Xcode自动播放一次警告声，并创建一个命名为的Debug标签的窗口，Xcode可在此展示调试区(Debug area)、调试导航器(Debug navigator)以及断点处的代码。


#### 控制执行 *Controlling Execution*
***

code允许您一行一行单步调试你的代码来查看特定执行阶段中应用的状态。使用调试区域(Debug area)来控制代码的执行，观察程序的变量和寄存器，观察控制台的输出并且与调试器交互。 你也可以使用调试区导航渲染帧的OpenGL调用，并查看特定调用的渲染状态信息。

通过点击工作区窗口工具条上视图选择器的中间按钮来展示调试区域(Debug area)。

![xcode7_2](/images/xcode7_2.png)

#### 查看状态信息 *Viewing State Information*
***

点击调试区工具栏中的暂停按钮（在暂停和继续之间切换）来暂停app的执行。想要设置断点，只需要打开源代码文件，并且点击你想暂停执行代码所在行的边列（Gutter）。边列中一个蓝色箭头会标识断点。如果想了解更多关于断点的信息，包括如何设置断点行为和不同类型的断点，请查看Breakpoint Navigator Help.

暂停应用后，当前正在执行的代码行会用绿色高亮。你可以使用调试区顶部条上的Step Over、Step Into、Step Out三个按钮来单步调试代码的执行。Step Over会执行当前行的代码行，包括任何的方法。如果当前的代码行调用了一个方法，step into会开始执行当前代码行，然后在到达被调用方法的第一行时停止。Step Out则执行当前方法或函数的剩余部分。

当暂停执行时，调试导航器会打开并展示一个堆栈追踪。选中其中一项，在编辑区和调试区中查看该项目的信息。当你调试时，可展开或收起线程来显示或隐藏堆栈框架。

![xcode7_3](/images/xcode7_3.png)

将指针悬停在源代码编辑器中的任何变量上，可查看一个显示着变量值的数据提示。点击变量旁边的Inspector图标(QuickLookInspectorIcon)，将对象的Objective-C描述打印至调试区控制台，并在一个额外弹出视图中展示。

![xcode7_4](/images/xcode7_4.png)

点击Quick Look图标(QuickLookVarIcon)观察变量内容的图形化展示。你可以针对自己的对象实现自定义的快Quick Look。

![xcode7_5](/images/xcode7_5.png)

####  查看内存越界 *Finding Memory Corruption*
***

![xcode7_6](/images/xcode7_6.png)

![xcode7_7](/images/xcode7_7.png)

#### *Debugging Metal*

#### *Debugging OpenGL*

当你在设备上构建并运行一个OpenGl ES应用时，调试区工具栏会包含一个Frame Capture 按钮（ ）。点击该按钮来捕捉一个frame。你可以使用OpenGL ES帧捕获做以下事情：

* 检查OpenGL ES 状态信息

* 内省OpenGL ES 对象，比如视图纹理和着色器。

* 在每次绘制调用之前单步调试状态调用，然后观察每个调用的变化。

* 单步调试绘制调用以准确查看如何构建图像。

* 在辅助编辑器中查看每个绘制调用使用哪些对象。

* 编辑着色器以查看应用程序上的效果。

以下截图展示已渲染帧的组件。左侧调试导航器显示部分渲染树，主调试器显示已渲染帧的颜色和深度资源，并展示其他一些图片资源。

![xcode7_8](/images/xcode7_8.png)


### 在运行时检查你应用的视图层次 [Examining the View Hierarchy](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/ExaminingtheViewHierarchy.html#//apple_ref/doc/uid/TP40010215-CH58-SW1)
***

点击在调试区顶栏的Debug View Hierarchy按钮来检查当前暂停应用的3D渲染视图分层。你可以：

* 通过在画布中点击并拖动来旋转该透视图。

* 使用左下方的滑动条增大或减小各视图层之间的间距。

* 使用右下方双滑块的滑动条改变可见视图的范围。滑动左滑块来改变最底层可见的视图，滑动右滑块来改变最上层可见的视图

* 按下展示剪切内容按钮来显示选中视图中被裁减的内容。

* 按下展示约束按钮来显示选中视图的任何Auto Layout约束。

* 使用放大（+）按钮和缩小（—）按钮来增加或减少透视图的放大倍数。

![xcode7_9](/images/xcode7_9.png)

### 检查应用对系统资源的影响 [Examining System Impact](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/ExaminingSystemImpact.html#//apple_ref/doc/uid/TP40010215-CH59-SW1)
***
调试导航器（Debug navigator）提供了能对应用程序性能进行深度分析的仪表。比如CPU仪表计量器展现了app的CPU的使用率，方便你侦测异常情况。根据应用的目的和功能，仪表计量器可以告诉你应用对内存、iCloud、OpenGL ES、电量以及CPU的影响。

![xcode7_10](/images/xcode7_10.png)

如果想要看详细的报告，可单击调试区的某个仪表计量器。如果你想要对你应用做更深层次的分析，请点击Profile In Instruments按钮。

![xcode7_11](/images/xcode7_11.png)

在问题区，电量报告会提供一个初步的诊断来告知你什么可能在严重损耗你的用电量。

![xcode7_12](/images/xcode7_12.png)

### 测量应用程序的性能 [Measuring Performance](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/MeasuringPerformance.html#//apple_ref/doc/uid/TP40010215-CH60-SW1)
***

Xcode中的Instruments程序会从在运行的应用中收集数据，并且展现在一个图形化的时间线上。使用Instruments，你可以收集性能方面的数据，比如你应用的内存使用，磁盘活动情况，网络活动情况和图形操作。通过把数据放在一起查看，你可以分析你应用表现的各个方面来找出潜在提升性能的可能。你也可以自动化测试iOS应用的界面元素。

![xcode7_13](/images/xcode7_13.png)

在Xcode几种方法来打开Instruments，比如：

* 从仪表计量器详细报告界面点击Profile in Instruments 按钮

* 选择Product>Profile

* 在一个scheme中的Profile项中指定一个Instrument

Instruments程序使用名为instruments的单独的数据采集模块，来随时收集某个进程的数据。Instruments程序有一个模板库，每个模板包括了为获取相关信息的一系列instruments。

![xcode7_14](/images/xcode7_14.png)

### 模拟问题 [mulating Problems](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/SimulatingProblems.html#//apple_ref/doc/uid/TP40010215-CH61-SW1)

***

iOS模拟器可帮你在设计和早期测试阶段找到主要的问题。举例来说，iOS模拟器的Debug菜单提供的多款工具可为你提供帮助：

* 减速一个动画来找出问题。

* 触发iCloud同步。

* 辨认出那些可能会有损你应用性能的混合视图层。

* 辨别出源像素没有对准到目标像素的图片

* 查看哪些内容在屏幕外渲染渲染。

* 模拟不同的地点。

![xcode7_15](/images/xcode7_15.png)

在iOS模拟器的任何模拟环境下，主屏幕都会提供打开iOS原生应用（比如Safari，Contacts，Maps和Passbook）的功能。你可以在iOS模拟器中初步的测试你的应用与这些应用的交互。举例来说，如果你正在测试一款游戏，可以使用iOS模拟器来测试这款游戏是否正确调用Game Center。

iOS模拟器中的辅助功能检视器（Accessibility Inspector）可帮助你不受个人制约的测试你应用的可用性。Accessibility Inspector显示你应用可访问的每个元素的信息并且可以模拟VoiceOver与这些元素交互。如果想打开Accessibility Inspector，点击iOS模拟器的主屏按钮然后点击设置>通用>辅助功能。将Accessibility Inspector右侧滑动按钮打开。

你可以在iOS模拟器通过改变语言来测试你应用的本地化。设置>通用>语言与地区>iPhone语言。

尽管你可以在iOS模拟器中测试你应用的基本功能，但是作为一个测试平台，由于诸多原因，模拟器还有很多限制。比如：

* 因为iOS模拟器是在Mac上运行，并使用电脑的内存，这远大于真机上的内存。

* iOS模拟器使用Mac的CPU运行而不是iOS真机的CPU。

* iOS模拟器并不运行真机上的所有线程。

* iOS模拟器无法模拟像加速度计，陀螺仪，摄像头，或者近距离传感器之类的硬件特性。

开发应用时，请务必在你想要支持的所有iOS真机和iOS系统版本上运行和测试。

### 自定义调试工作流 [Customizing Your Workflow](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/CustomizingYourWorkflow.html#//apple_ref/doc/uid/TP40010215-CH62-SW1)
***

通过Xcode Behaviors来偏好定制Xcode的行为。选择Xcode> Behaviors，自定义在建立、运行和调试应用时Xcode该做的事。

比如，Xcode可以在你代码在断点暂停时显示调试区域或者在建立应用失败时，显示问题导航器

下面截图中展示了当代码暂停时，Xcode行为是怎么自定义的下面有些自定义行为的例子。

* 每次暂停时播放一个提示音。

* 在工作区域窗体中创建一个名为Debug的标签来展示调试导航器。

* 在Debug标签中同时展示变量视图和控制台视图。

* 在Debug标签中隐藏Utilities区域。

![xcode7_16](/images/xcode7_16.png)

当你设置了上面的行为后，当项目中的代码碰到断点时，Xcode在工作区窗口创建一个debug标签，里面显示特定的内容

![xcode7_17](/images/xcode7_17.png)

你可以自定义Xcode的行为，这些自定义行为可以由菜单中的选项或者绑定的快捷键触发。选择Xcode > Preferences， 选择Behaviors偏好窗口，然后点击底部的Add（+）按钮。输入新行为的自定义名称然后按下Return。在右侧复选框中勾选当你触发这个行为时你想让Xcode做的事。比如，建立一个名为Unit Testing的行为用来保存你工程的快照并且运行你的单元测试。当你建立这个行为后，它会出现在Xcode> Behaviors菜单中。

想给自定义行为添加个快捷键的话，选择Xcode > Preferences然后点击Key Bindings。在Key Bindings偏好窗口中，选择Customized标签找到你自定义的行为。在文本框中，键入快捷键然后点击文本框以外的地方完成操作

## 测试 [Testing](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/UnitTesting.html#//apple_ref/doc/uid/TP40010215-CH63-SW1)

***

### 使用单元测试 [Using Unit Tests](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/UnitTesting.html#//apple_ref/doc/uid/TP40010215-CH63-SW1)

***

Xcode支持三种主要测试类型：主要针对代码功能的功能测试，以及测量运行时间的性能测试，以及用户界面的测试。前两种测试都需要你来编写。每种函数都设置了测试环境，对app进行有针对性的测试。

最常用的功能测试是单元测试。代码单元是最小的可测试组件，比如类或者方法集中用来实现基本目的的方法。单元测试通常用来检测代码更改产生的回归。一些开发者首先编写单元测试，然后执行了通过测试的方法。性能测试主要用来衡量app在不同类型设备上完成任务所需的时间。Xcode会根据不同的配置和您选择的基准性能标准来跟踪时间。

测试用例以一个特定方式来运行代码单元或者检测app性能某个特性部分，如果测试结果跟预期结果不同，那么这就是个失败的测试用例。一个测试包由一组测试用例组成。

当你创建项目或者对象（target）时，Xcode会在构建应用程序的scheme中包含一个单元测试对象。对象的实现文件包含setUp、tearDown以及testExample方法的存根。完成这些存根实现，并根据需要为执行应用程序上的单元测试添加其他代码。

通过选择Product > Test来运行所有测试。点击测试导航器图标来查看状态和测试结果。点击测试导航栏右下角的按钮（+）为项目添加测试对象（或者为测试添加类）。想要查看特定测试的源码，请在测试列表中选中，源码编辑器将会打开相应的文件。

![xcode8_1](/images/xcode8_1.png)

想要运行一个测试包，请点击名称右边的箭头。想要运行测试方法的子集，请在测试导航器中选中它，然后选中Product > Perform Action > Run Test Methods。想运行单个测试方法，可点击方法名右边的箭头。选择Product > Test来运行scheme中所有测试。

测试运行成功后，测试名称后边会出现一个带有复选框的绿色菱形。如果测试失败，测试名称右边会出现一个带有X的红色菱形，并且测试中存在的问题会出现在问题导航器中，点击问题导航器按钮即可查看详细问题。

如果仅想查看失败的测试，可点击测试导航器底部的Failed Test按钮（FailedTestIcon）。选中失败的方法便可在源码编辑器中详细查看。解决了造成测试失败的问题后，点击表示失败测试的指示器-带有X的红色菱形-来重新运行测试。

在辅助弹出菜单选中Test Classes 或者Test Callers类别，即可在辅助编辑器中展示相关的测试方法。

### 使用持续集成工作流 [Using Continuous Integration Testing](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/ContinuousIntegrationTesting.html#//apple_ref/doc/uid/TP40010215-CH64-SW1)

***

Xcode通过Xcode service支持持续集成工作流。Xcode service是OS X Server中的服务，可以自动一体化编译、运行单元测试、执行静态分析以及归档产品。Xcode service会报告编译错误和警告、静态分析器问题、以及失败的单元测试。所有测试、分析以及归档都在服务器上执行。

![xcode8_2](/images/xcode8_2.png)

### 使用代码覆盖率 [Using Code Coverage](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/CheckingCodeCoverage.html#//apple_ref/doc/uid/TP40010215-CH74-SW1)

***

Code coverage是一个计算你的单元测试覆盖率的工具。高水平的覆盖给你的单元测试带来信心，也表明你的应用被彻底的测试过了。你可能写了几千个单元测试，但如果覆盖率不高，那么你写的这套测试可能价值也不大。

![xcode8_3](/images/xcode8_3.png)

![xcode8_4](/images/xcode8_4.png)

![xcode8_5](/images/xcode8_5.png)

###  记录UI测试 [Recording UI Tests](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/RecordingUITests.html#//apple_ref/doc/uid/TP40010215-CH75-SW1)
***

![xcode8_6](/images/xcode8_6.png)

#### *Recording a Test*

![xcode8_7](/images/xcode8_7.png)

![xcode8_8](/images/xcode8_8.png)
