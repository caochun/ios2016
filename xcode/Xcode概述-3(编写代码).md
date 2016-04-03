title: Xcode 编写代码
date: 2015-10-04 18:26:47
category: xcode概述
tags:
---
Xcode 概述
<!--more-->

## 在源码编辑器中编写代码 [Writing Code](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/AddingandOpeningFiles.html#//apple_ref/doc/uid/TP40010215-CH35-SW1)

***
### 打开和添加文件 [Opening and Adding Files](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/AddingandOpeningFiles.html#//apple_ref/doc/uid/TP40010215-CH35-SW1)
***

要查看和编辑源码文件，请在工程导航器中选中文件，文件的内容则会展示在工作区窗口的编辑区域。

![xcode3_1](/images/xcode3_1.png)

#### 通过模板来创建源文件 *Creating Source Files from Templates*
***
使用文件模板来添加文件到您的项目中是最省心的办法。要访问文件模板库，请单击工作区窗口的实用工具区的文件模板按钮![xcode3_2](/images/xcode3_2.png)，并将这些模板拖曳到项目导航器中来创建源文件。

![xcode3_3](/images/xcode3_3.png)

可以选择 File > New File 或者使用 Command + N 的快捷键来创建源文件。Xcode 将打开一个 New File 对话框，您可以从中选择合适的模板来创建文件。选择完模板后单击 Next 按钮，给文件命名后就可以将其添加到项目中了。

![xcode3_4](/images/xcode3_4.png)

![xcode3_5](/images/xcode3_5.png)

#### 快速打开文件 *Opening a File Quicking*
***
选择 File > Open Quickly 来查找一个定义特殊符号的文件，也可以选择一个名称含有特定字符的文件。Open Quickly 搜索栏不区分大小写，并且搜索范围仅限于当前项目和已激活的软件开发包（SDK）。您可以在搜索结果列表中双击文件来打开它们。
![xcode3_6](/images/xcode3_6.png)

要打开辅助编辑器窗格中的文件，请在双击时按住 Option 键。要在一个单独的窗口中打开文件，请按下Option + shift 键。要查看能让您指定应在何处打开文件的对话框，请按住 Option + shift 键并单击。

#### 拆分编辑器窗口来显示相关内容 *Splitting the Editor to Display Related Content*

***
拆分编辑器窗口以便能够查看一个文件的多个视图，亦或者是能一次查看多个相关文件。例如，您可以同时查看某个实现文件以及其对应的头文件。要拆分代码编辑器，可点击工作区工具栏上的辅助编辑器按钮（![xcode3_7](/images/xcode3_7.png)）来打开辅助编辑器窗口。您可以选择垂直拆分还是水平拆分。

![xcode3_8](/images/xcode3_8.png)
![xcode3_9](/images/xcode3_9.png)

如果要改变拆分的方向的话，选择 View > Assistant Editor，然后选择其中一项菜单设置。在上面两个截图中，我们关闭了导航栏和工具栏以最大程度地显示代码编辑器区域。

#### 设置辅助编辑窗口 *Setting the Assistant Editor Mode*
***

当打开辅助编辑器窗口时，您可以将其设置为两种模式：手动或跟踪。在手动模式下，您通过跳转栏选择要显示的文件。即使您改变了主编辑器的内容，辅助编辑器中的内容也不会改变。

在跟踪模式下，您可以从弹出菜单中选择一种标准。这个标准含有一些内含组，比如说副本、父类、子类以及同级类。一旦您选中了一个标准，那么 Xcode 将会在子菜单中列出相应的文件。当您改变了主编辑器中的文件时，Xcode就会基于选中的标准来更新辅助编辑器。

要更改模式，请选择辅助弹出菜单中的某一项。（辅助弹出菜单是辅助编辑器跳转栏中前进和后退按钮右边的第一个项目）

![xcode3_10](/images/xcode3_10.png)

您可以通过点击辅助编辑器窗格右上方的添加按钮![xcode3_12](/images/xcode3_12.png)来进一步分割辅助编辑器窗格。一旁的关闭按钮![xcode3_12](/images/xcode3_12.png)则将其关闭。

![xcode3_11](/images/xcode3_11.png)

### 编辑源代码 [Editing Source Code](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/EditingSourceCode.html#//apple_ref/doc/uid/TP40010215-CH34-SW1)
***

#### 键入时修正错误 *Fix Errors as You Type*
***
当你在源码编辑器中进行输入时，Xcode会对文本进行扫描。当你出现语法错误时，Xcode会以红色下划线或者插入符号标记。点击错误之处，Xcode则会展示对问题的描述信息。

![xcode3_13](/images/xcode3_13.png)

通常，Fix-it可自动修复错误。选中推荐的修复方案，按下Return键接受修复。在上方的屏幕截图中，Fix-it建议在文本字符串之前插入“@”字符。更多信息，请查看 Catching Mistakes with Fix-it.

#### 使用代码补全功能加快输入 *Speed Up Typing with Code Completion*
***
当您开始键入某个符号名符号时，Xcode 会提供内联建议以补全其名称。单击建议栏中的某项来选中它，或者使用向上或向下键来更改选中的建议。按下 Return 键接受该建议。

![xcode3_14](/images/xcode3_14.png)

当一个方法或者函数含有参数或者引用时，代码完成功能将用占位符来替代每个参数。要在这些占位符中跳转，请选择 Navigate > Jump to Next Placeholder（或者 Navigate > Jump to Previous Placeholder）。另外，使用 Tab 键可以跳转到下一个占位符，Shift + Tab 键跳转到上一个占位符。

#### 自动配对花括号、圆括号以及方括号 *Match Pairs of Braces, Parenthese, and Brackets Automatically*
***
Xcode 帮助您自动配对分隔符，比如：

* 将鼠标指针放在源代码编辑器左边缘的焦点范围带上。Xcode 高亮显示该位置的括号范围，如前面的屏幕截图所示。
* 键入一个左括号，Xcode 将会在键入换行符之后插入右括号。
* 键入一个右括号或者其他分隔符，Xcode 将简要强调其对应的分隔符。
* 使用向右箭头键将插入点移动到结束分隔符后面，Xcode会暂时高量强调其对应的分隔符。
* 选择 Editor > Structure > Balance Delimiter。Xcode 将选择插入点附近的文本，其中包括最近的一组封闭分隔符。
* 双击任意一个分隔符。Xcode 将选中由分隔符以及其对应分隔符所封闭的全部文本。


#### 在您的文件中插入代码片段 *Drop Code Snippets into Your Files*
***
您可以使用代码片段快速键入源码文本。您可以从Code Snippet Library中直接将代码片段拖放至源码文件中。想要访问Code Snippet Library，请在工作区窗口的实用工具区点击Code Snippet标识按钮（04.png）。Code Snippet Library提供了有用的标准的代码片段，比如屏幕上展示的switch语句代码片段。想要将自己的代码片段添加至代码片段库中，并添加快捷键，请查看Source Editor Help.

![xcode3_15](/images/xcode3_15.png)

#### 使用手势和快捷键 *Use Gestures and Keyboard Shortcuts*
***

使用手势和快捷键可以简化并增强您对源代码编辑器的使用。除了在 OS X 系统上常见的 Multi-Touch 手势，下列这些手势在源代码编辑器中尤为适用：

* 两指轻按可以打开编辑器的上下文菜单（还可以通过Control-click或使用鼠标左键单击显示）
* 两指向上或向下轻扫垂直滚动，以及左右水平滚动。
* 三指轻扫导航栏可以在编辑器中打开任何文件。向左轻扫显示前一个文件，向右轻扫显示后一个文件。

键盘序列提供了很多在 Xcode 中常见的菜单命令快捷键。例如，按住 Shift + Command + O 键可以从 File 菜单中调用 Open Quickly 命令，按住 Shift + Command + D 键可以从 Navigate 菜单中调用 Jump 命令。还有一些在编辑操作中的快捷键。例如，Control + K 可以删除从插入点到行尾的所有字符。

快捷键通过键值绑定来建立，您可以选择 Xcode > Preferences 然后选择 Key Bindings 来查看和修改快捷键。

### 搜索和替代 [Search and Replace](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/SearchandReplace.html#//apple_ref/doc/uid/TP40010215-CH36-SW1)
***

Xcode 提供了几种方法来适用于多行文本修改。

#### 文件中替代 *Searching in a File*
***
通过选择 Find > Find and Replace 来更改一个文件中的文本字符串实例。

![xcode3_16](/images/xcode3_16.png)

#### 编辑所有的符号 *Editing All Symbols*
***
您可以同时修改某一范围内出现的所有相同的符号名称，比如说局部变量或者参数名。将插入符放在您想要编辑的符号上，当三角形符号出现时，单击它来显示出菜单，然后选择 Edit All in Scope。接下来编辑该符号。当您输入新的内容后，该符号的所有实例都将同时改变。

![xcode3_17](/images/xcode3_17.png)


#### 项目中替代 *Searching the Project*
***
您可以通过选择项目中的 Find > Find and Replace 项来改变项目或者工作区中的文本字符串实例。这个命令将显示查找导航器。您可以自定义其操作--例如限制搜索范围，或者按大小写来匹配字符串。查找导航器提供了一个预览，允许您替换字符串的所有实例或者接受还是拒绝某一单独替换。

![xcode3_18](/images/xcode3_18.png)

#### 使用字符串模式 *Using Wildcards*
***

您可以在搜索区使用通配符字符串模式。要进入该模式的某个部分，单击查找检索区左侧的小三角形，然后选择 Insert Pattern 。从模式弹出菜单中选择一项。Xcode 将在查找到的字符串中的当前光标位置插入该通配符。

![xcode3_19](/images/xcode3_19.png)

#### 重构代码 *Refactoring Code*
***

您可以重构您的代码以改善其结构、增强易读性和可维护性而不改变其行为。重构操作（也称为变换）被应用到您在代码编辑器中选择的某个代码片段或符号上。您可以重命名符号、提取代码并放到方法中、创建父类、移动项目到父类或子类，以及在整个项目文件范围内封装变量。

在选择完需要重构的代码片段或符号后，选择 Edit > Refactor，然后选择合适的重构命令。预览面板将显示应用重构时代码会出现的变化。在预览对话框的左窗格中取消某个文件可以将其从重构操作中移除。您可以在预览中直接编辑您的源代码。所有的修改操作将在预览中显示，并且其会包含在重构操作中。

![xcode3_20](/images/xcode3_20.png)

### 管理符号 [Working with Symbols](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/WorkingwithSymbols.html#//apple_ref/doc/uid/TP40010215-CH37-SW1)
***

#### 显示符号的定义 *Display the Definition of a Symbol*
***

将鼠标指针放到一个符号上，然后按住 Command 键并单击来显示这个符号的定义。源代码编辑器将导航到该符号的定义中，并将其高亮显示。如果该定义位于单独的文件中，那么代码编辑器将会显示这个文件（亦或者将鼠标指针放到符号上，然后选择 Navigate > Jump to Definition）。

将鼠标指针放到一个符号上，然后按住 Command + Option 键并单击，就可以在辅助编辑器窗格中显示其定义，如截图中所示的APALoadFramesFromAtlas函数。这个方法可以让您在查看符号定义时保持该符号一直在视图中。

![xcode3_21](/images/xcode3_21.png)

#### 查看某个符号的相关文档 *Look Up Documentation for a Symbol*
***

您可以通过将插入点放到符号上来查看其参考文档，比如说方法或属性。在检查器窗格工具栏中选择 Quick Help 按钮（）。如果检查器窗格没有打开，那么可在主工具栏中单击该按钮来以在工作区配置按钮集中显示该导航。符号的 Quick Help 项出现在工具区。

文档信息包括针对该符号的完整参考文档链接、声明该符号的头文件、相关的编程指南、以及相关的示例代码。（按住 Option 单击该符号，以查看弹出窗口中的信息概要，即声明、符号的描述信息、其所有返回值、其可用的 SDK版本、头文件以及相关参考文档的链接）。

![xcode3_22](/images/xcode3_22.png)

单击 Quick Help 中的链接，Xcode 将会打开一个单独的 Xcode 文档查看器窗口。Xcode 的文档查看起提供了访问信息的快捷步骤，而无需将您的注意力从正在编辑的文件中离开。

![xcode3_23](/images/xcode3_23.png)

除了详细的框架API参考外，文档查看器还包括苹果工程师提供的完整编程指南、教程、示例代码以及视频演示。在类引用中单击靠近查看器顶部的“More related items（更多相关项）”来跳转到与您的任务相关的另一个文件中。

![xcode3_25](/images/xcode3_25.png)

使用工具栏上的搜索栏来查找关于 API 或者编程概念的额外信息。

要在一个消息中内含一个指向该文档的链接，单击分享按钮![xcode3_24](/images/xcode3_24.png)，然后选择电子邮件链接或信息。您可以在 Safari 中以 HTML 或 PDF 格式打开。对于示例代码项目来说，单击窗口顶部的 Open Project 来下载该项目然后在 Xcode 中打开.

![xcode3_26](/images/xcode3_26.png)

### 分析您的代码 [Analyzing Your Code](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/AnalyzingYourCode.html#//apple_ref/doc/uid/TP40010215-CH38-SW1)
***

#### 使用代码折叠来检查代码 *Examining the Structure of Your Code with Code Folding*
***

您可以通过隐藏源代码的其他部分，来让自己更容易将注意力集中在源代码的特定函数或方法上。选择 Editor > Code Folding > Fold Methods & Functions。定位到您想要折叠的方法上，然后双击它的省略按钮来折叠该方法。下面的截图显示了configureConnectedGameControllers方法的折叠。

![xcode3_27](/images/xcode3_27.png)

将鼠标指针移动到编辑器左边缘上，它将会在焦点框中显示一个焦点范围带——比如说截图中的for声明。范围外的代码将会用阴影覆盖。

#### 进行静态代码分析 *Performing Static Code Analysis*
***

您可以在运行应用前使用静态分析器查找代码中的bug。静态分析器可在数秒内尝试上千种可能的代码路径，然后报告可能隐藏得很深的错误，或者是几乎不可能被复制的 bug。静态分析器同样还将确定出您代码中没有遵守 API 推荐使用方式的区域，比如Foundation、UIKit 以及AppKit 等API的语言风格。

要执行静态代码分析的话，请选择 Product > Analyze。Xcode 的静态分析器将解析程序的源代码，并确定这些问题类型：

* 逻辑错误，如访问未初始化的变量和取消对空指针引用。
* 内存管理错误，如分配内存泄露
* 死存储（未使用的变量）错误
* 由不遵循项目正在使用的框架和库所需的策略所引发的 API 用法错误。

静态分析器将在问题导航栏中报告错误，您可以在项目导航栏中单击问题导航栏按钮来激活这个视图。在问题导航栏中选择一个分析器消息，以在源码编辑器中显示相关的代码。在源码编辑器中点击相应的消息，然后使用源码编辑器上方的分析结果栏中的弹出菜单来研究错误路径和原因。接着编辑代码以修复错误。

### [Customizing the Editor](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/CustomizingtheEditor.html#//apple_ref/doc/uid/TP40010215-CH39-SW1)
***

#### 选择字体和文本颜色 *Choosing Syntax-Aware Fonts and Text Colors*
***

Xcode 基于编程语言来分析代码，并为每个标记或字符串分配一个句法标签。例如，项目中的每一个注释、关键字以及类名都将被定义。Xcode 为每个句法标签类型分配一种颜色和字体以让代码易于阅读。您可以通过选择 Xcode > Preferences 然后选择 Fonts & Colors 项来选择多种字体和颜色。例如，Presentation 主题增加了字体大小以让屏幕上的项目文本更易阅读。您可以创建自定义的字体和颜色主题。

![xcode3_28](/images/xcode3_28.png)

#### 自定义编辑和缩进选项 *Customizing Editing and Indenting Options*
***
您可以更改源代码编辑和缩进设置，以适应您的喜好。选择 Xcode > Preferences，然后选择 Text Editing 来修改如下配置：

* 在源代码编辑器边列显示行数
* 在您输入后自动插入右括号
* 当您输入代码时显示代码补全建议
* 使用空格或制表符缩进
* 虚换行(soft-wrap)线
* 执行语法感知缩进

### 获取编辑器帮助 [Finding Editor Help](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/FindingEditorHelp.html#//apple_ref/doc/uid/TP40010215-CH40-SW1)

***
可以在 Xcode 中直接显示步进说明，以帮助执行常见的源码编辑器任务。在源码编辑器的任意位置按住Control单击，便可以在一个列表中查看一系列常用指令。选择 Show All Hlep Topics 以查看所有关于源代码编辑器的帮助文章。选择某一项任务，然后帮助文章将会出现在 Xcode 的文档查看器窗口中。

![xcode3_29](/images/xcode3_29.png)

您可以在Xcode中使用快捷菜单获得Xcode帮助文章。在主界面任何地方按下Control键并单击鼠标，则可以看到适用于该区域的帮助文章列表。

![xcode3_30](/images/xcode3_30.png)
