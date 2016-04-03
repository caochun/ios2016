title: Xcode 工作区窗口
date: 2015-10-06 18:11:47
category: xcode概述
tags:
---
Xcode 概述
<!--more-->

## 工作区窗口[The Workspace Window](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/TheWorkspaceWindow.html#//apple_ref/doc/uid/TP40010215-CH25-SW1)

***
### [Workspace Window Overview](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/TheWorkspaceWindow.html#//apple_ref/doc/uid/TP40010215-CH25-SW1)
***
Xcode工作区可用来执行核心开发任务，它是创建和管理工程的主界面。工程是Xcode开发中的主要单元，包含了构建应用程序所需的所有元素、框架、插件以及其他软件产品，并维系这着这些元素之间的关系。关于工程的更多详细信息，请参看： A Project Is a Repository of Files and Resources for Building Apps.

Xcode的工作区可以自动适应其手头上的任务，您可以更进一步配置窗口使之适合自己的工作风格。您可以根据需要打开多个工作区。

工作区窗口组件如下图所示：

![xcode1_1](/images/xcode1_1.png)

工作区窗口包含编辑区。当您选中工程中的一个文件时，其内容会出现在编辑区，Xcode会在适当的编辑器中打开文件。比如上图中，在工作区窗口左侧的导航器中选中一个Swift代码文件，右侧的编辑区则会包含AdventureScene.swift。

工作区窗口最多可展示3个可选区域，用于在开发周期中执行不同的任务。隐藏不用的区域可帮您更好地专注于当前的任务。您可以通过工具栏最右端的工作区配置按钮隐藏或者展示可选区。

* 展示和隐藏导航区域（navigator area）。您可以在导航区遍历整个工程，包括文件、符号、断点、编译问题、测试以及编译报告等，也可以搜索工程中的任何字符串。

* 展示和隐藏调试区（debug area）。您可以在调试区查看变量，与调试终端进行交互，以及控制应用程序的执行。

* 展示和隐藏实用工具区（utilities area）。您可以在该区域检查或更改文件的属性、图形UI元素、sprites以及项目中的其他元素，也可以用来访问现成的资源库，请参看： Access Resources and Inspect Elements in the Utilities Area.

### 在工作区导航[Navigating Your Workspace](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/NavigatingYourWorkspace.html#//apple_ref/doc/uid/TP40010215-CH26-SW1)

您可以在导航面板中访问工程中的文件、符号、单元测试、诊断以及其他方面。在导航栏中，您可以选择适合自身任务的导航器，并在每个导航器的内容区（content area）访问工程相关的部分，而且每个导航器的filter bar则可以让您限制内容的展示。

![xcode1_2](/images/xcode1_2.png)

Navigator bar中包含以下选项：

* 工程导航器（Project navigator）：在工程中添加、删除、分组以及管理文件，或者查看文件，或者在编辑区编辑其内容。

* 符号导航器（Symbol navigator）：以列表或者层级形式浏览工程中的符号。可通过Filter bar左侧的按钮将符号限制在任意类或者协议的组合，或者仅展示工程中的符号，或者仅展示容器（containers）。

* 搜索导航器（Find navigator）：使用搜索或者过滤功能快速查找工程中的任何字符串。

* 问题导航器（Issue navigator）：可查看在打开、分析以及构建项目过程中发现的诊断、警告以及错误问题。

* 测试导航器（Test navigator）：创建、管理、运行以及检查单元测试。

* 调试导航器（Debug navigator）：检查项目执行过程中某个指定点或指定时间的运行线程和相关的堆栈信息。

* 断点导航器（Breakpoint navigator）：通过指定特征（比如触发条件）来微调断点。

* 报告导航器（Report navigator）：查看构建、运行、调试、持续集成以及源码控制相关历史信息。

在Filter bar文本输入区键入文本，则会在内容区（Content area）展示包含该检索词的项目。大部分导航器在filter bar左侧展示按钮，用以进一步限制所展示的内容。部分filter bar左侧有一个“+”的按钮，可用来在content area中添加元素。报告导航器中filter bar左侧的按钮用来与bots进行交互。关于报告导航器中Bots的用法详情请参看Xcode Continuous Integration Guide中Manage and Monitor Bots from the Report Navigator一节。

在Content area选中文件并查看或者编辑文件。

### 编辑工程文件[Editing Your Files](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/EditingYourFiles.html#//apple_ref/doc/uid/TP40010215-CH27-SW1)

Xcode中大部分编辑工作发生在编辑区，该区域是工作区窗口中主要的可视化区域。最常使用的编辑器有：

* 源码编辑器（Source editor）：用以编写源代码。

* Interface Builder：用以图形化地创建和编辑用户界面文件。

* 工程编辑器（Project editor）：用以查看和编辑应用程序的构建方式，比如制定构建选项、目标架构以及app entitlements。

在导航器的内容区选中文件，Xcode会在相应的编辑器中打开文件。在截图中，我们在project navigator中选择文件iPhoneStoryboard.storyboard，那么会在Interface Builder中打开该文件。Interface Builder在左侧展示大纲视图，并在右侧展示画布（canvas）。更多信息请参看Build a User Interface。（可选的实用工具区和调试区被隐藏，以便最大化导航器和编辑器的空间）

![xcode1_3](/images/xcode1_3.png)
以下截图展示了若干出现在搜索导航器内容区的搜索结果。选中其中一项结果，其文本字符串就出现在源码编辑器中。
![xcode1_4](/images/xcode1_4.png)

#### 配置编辑区域
使用工具栏右侧的编辑器配置按钮，并根据既定的任务来配置编辑区域。

* 标准编辑器（Standard editor）：使用选中文件的内容填充编辑区。

* 辅助编辑器（Assistant editor）：在标准编辑器面板中展示一个逻辑上与内容相关的单独的编辑器面板。您可以更改其内容。

* 版本编辑器（Version editor）：在一个面板中展示当前选文件，在第二个面板中展示该文件的另一个版本，以便比较两者之间的差异。只有当您的工程支持源码控制的时候，该编辑器才起作用。

下图是一个在标准编辑器面板中打开的执行文件APAAdventureScene.m。隐藏了导航区、调试区以及工具区3个可选的工作区，最大化了编辑区的内容展示。在源码编辑器中，辅助面板展示了执行文件相关的头文件APAAdventureScene.h.

![xcode1_5](/images/xcode1_5.png)

#### 使用跳转栏

每个编辑器或者辅助编辑器面板都包括一个跳转栏--一个交互式的分层机制，用以直接跳转至工程中任意层次结构中的某个项目。跳转栏的配置和行为可根据上下文环境

定制。一个基本的跳转栏配置由3部分组成：

1. 相关项目菜单提供了与当前上下文环境相关的附加选项，比如最近打开的文件或者您正在编辑的执行（.m）文件的接口（.h）文件。

2. XC_O_jumpbar_next_prev_buttons用来在导航历史中查看上一个或者下一个文件。

3. 分层路径菜单允许您通过跳转至一个新项目来更改编辑器或者辅助编辑器面板中展示的内容。根据您点击的路径，它可以由一个或者多个分段组成。


点击分层路径菜单中的某个分段（segment）可看到相关项目的弹出菜单。比如，如果分段可识别工程的名称，那您可以在工程中使用跳转栏导航至某个文件或者打开任何一个文件。如果分段可识别文件夹的名称，那您可以使用跳转栏打开文件夹内的文件。如果分段可识别源码文件的名称，那您可以在当前打开的文件中使用跳转栏来展示并选中符号。

![xcode1_6](/images/xcode1_6.png)

### 在实用工具区访问资源和检查元素

实用工具区位于工作区窗口的最右边，您可以通过它快速访问以下资源：

* Inspectors,用以查看和更改编辑器中打开的文件的属性（特性）。

* 现成的库-可用在工程中的现成库。

下图中，实用工具区面板的顶端是Inspectors，底部面板中放置的是可访问使用的库。
![xcode1_7](/images/xcode1_7.png)

使用inspector栏选择最适用于您当前任务的检查器。通常情况下，您通常会在检查器栏中看见两个检查器，其余检查器在其他编辑器中可见。

* 文件检查器（File inspector）：用以查看和管理选中文件的元数据。尤其是要本地化storyboards和其他媒体文件，并更改用户界面文件设置时。

* 快速帮助（Quick Help）：查看符号的细节信息、界面元素，或者在文件中构建设置。比如Quick Help展示对方法的简明描述，该方法何时在何处被声明，该方法的范围，它所需的参数，以及适用平台和可用的架构。

使用library bar 访问现有的资源库：

* 文件模板（File templates）：普通类型文件和代码结构的模板。

* 代码片段（Code snippets）：用以储存您软件中用到的源代码片段，比如类声明、control flows、block声明以及苹果公司常用的模板。

* （对象）Objects：应用程序用户界面的项目。

* （媒体）Media：包含图形、图标、声音文件以及诸如此类的文件。

想要在您的项目中使用现成的库，可将其直接拖拽至适当的区域。比如，您要使用代码片段，可将其从库中直接拖放到源码编辑器中；想要使用文件模板创建一个源码文件，可将其模板拖放至工程导航器中。

想要限制某个被选中库的项目展示数，可在 filter bar的文本域输入相关的文本进行限制。比如，输入“button”来展示对象库中的所有按钮。

### 使用工作区工具栏管理常见任务
工作区窗口顶部的工具栏可让您快速访问频繁使用的命令。“Run”按钮可构建和运行您的产品。“Stop”按钮可终止代码的运行。“Scheme menu”可让您配置您想要创建和运行的产品。“Activity viewer”通过展示状态信息来展示当前任务执行的进程、构建进程以及您项目的其他信息。

到此，您已经清楚了编辑器配置按钮如何配置编辑器区域，已经了解了工作区配置按钮如何隐藏或者展示可选的导航器区、调试区以及实用工具区。

![xcode1_8](/images/xcode1_8.png)

View菜单包括隐藏或者展示工具栏的命令。

![xcode1_9](/images/xcode1_9.png)

### 使用多个Tab或者多个窗口

使用Safari风格的tab来实现工作区窗口多重的工作流指定的布局。比如，在下方的截图中，活跃标签展示了资源编辑器中执行文件(APAViewController.m) 的内容，右端的是头文件(APAViewController.h)，左边是app storyboard(iPhoneStoryboard.storyboard)。点击某个tab，其对应的编辑器则会成为当前的活跃编辑器。

![xcode1_10](/images/xcode1_10.png)

View菜单包含了展示和隐藏tab的命令。创建一个tab，可选择File > New > Tab。想要移除tab，请将指针放在tab上并点击关闭按钮即可。

想要创建多个工作区窗口，可选择 File > New Window。可定义每个tab或窗口，比如使用工具栏中的Hide/Show实用工具按钮(XC_O_utilities_button_2x.png )展示或隐藏实用工具区。

![xcode1_11](/images/xcode1_11.png)

![xcode1_12](/images/xcode1_12.png)
