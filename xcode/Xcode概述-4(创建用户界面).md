title: Xcode 创建用户界面
date: 2015-10-03 18:26:47
category: xcode概述
tags:
---
Xcode 概述
<!--more-->

## 构建用户界面 [Building a User Interface](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/UsingInterfaceBuilder.html#//apple_ref/doc/uid/TP40010215-CH42-SW1)
***

### 使用Interface Builder [Using Interface Builder](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/UsingInterfaceBuilder.html#//apple_ref/doc/uid/TP40010215-CH42-SW1)
***

开发者可使用Interface Builder创建应用程序的用户界面。在工程导航器中打开一个界面文件，文件内容会在工作区窗口的编辑区域的Interface Builder中打开。用户界面文件的扩展名为.storyboard或.xib，xib文件通常会指定一个视图控制器或菜单栏，storyboard文件则指定了一系列视图控制器及其跳转关系。与xib不同，storyboard可以包含用户界面所有的视觉元素。当你使用Xcode内建的模板创建新工程时，会提供一个默认的用户界面文件。

![xcode4_1](/images/xcode4_1.png)

code以 XML格式储存xib和storyboard文件内容。编译时，Xcode将xib和storyboard文件编译成二进制文件，即nib文件。运行时，nib文件会被载入并实例化来创建新的视图。

想要添加用户界面元素，可从实用工具区将元素拖放至Interface Builder画布上，你可以在此对齐元素，为其设置属性，以及为元素之间和源码文件中的代码建立联系。在Interface Builder中布局好界面所需元素后，你可以在辅助编辑器中编写代码实现其行为。

![xcode4_2](/images/xcode4_2.png)

#### IB的组成部分 *Parts of Interface Builder*
***

Interface Builder有两个主要区域，左边的dock栏和右边的canvas。dock栏列出了用户界面文件包含的对象，canvas用于对app用户界面中的对象进行布局。

![xcode4_3](/images/xcode4_3.png)

dock栏中的大纲视图展示了更高级别对象中嵌入的对象。

![xcode4_4](/images/xcode4_4.png)

对于xib文件，你可以点击Interface builder左下角的Show Document Outline按钮(DockViewControl)，从而以icon视图形式展示高级对象，而不是大纲视图。

![xcode4_5](/images/xcode4_5.png)

对于storyboard文件，大纲视图的顶级项目对应画布上的顶级视图控制器或场景。隐藏大纲视图后，Storyboard文件则不会展示icon视图。Storyboard上的每个场景在画布上都有一个对应的高级对象视图，如下图所示，icon视图中的项目从左到右依次对应场景、场景中的first responder以及该场景的退出segue。更多信息详见Design the User Interface of Your App with Storyboards.

![xcode4_6](/images/xcode4_6.png)



#### 添加界面对象 *Adding Interface Objects*
***

要往用户界面中添加内容，先点击工作区窗口中工具栏的按钮打开实用工具区，然后点击工具库栏中的按钮调出对象库，然后选择一个对象拖入到视图中，在下图中，我们从对象库中拖放一个视图控制器到画布上。

![xcode4_7](/images/xcode4_7.png)

添加对象后，你可以拖住其边角来改变其大小。移动对象时，会出现一些蓝色虚线来帮助你定位和布局对象。在对象库栏上方是Interface Builder检查器，你可以用它设置对象外观和行为，在下图中，我们用属性检查器（Attributes Inspector）按钮(AttributesInspectorSelected)指定按钮的自定义类型

![xcode4_8](/images/xcode4_8.png)

#### 查找和替代字符串*Finding and Replacing Strings*
***

### 使用storyboard来设计应用的界面 [Designing with Storyboards](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/DesigningwithStoryboards.html#//apple_ref/doc/uid/TP40010215-CH43-SW1)
***
您可以使用storyboard来可视化地布局用户在iOS或Mac 应用中的路径，使用Interface Builder按照下述内容指定用户界面：

* 场景
* 场景间切换
* 触发场景切换的控件

场景表示屏上内容区域。在iPhone或iPod touch上面，一个屏幕通常只包含一个场景。在iPad或Mac上面，一个屏幕可以由一个以上的场景组成。Segue表示一个场景到另一个场景的切换。

下图表示了使用Xcode 的Master-Detail应用模板创建iOS项目时所提供的默认storyboard，它包含三个场景和两个segue。最左边的场景是一个导航控制器，用于管理用户在主界面和详细页间的导航。使用这个模板时，你可以按需从对象库中添加额外的视图控制器，并使用Identity inspector配置拖放到画布中的视图控制器。

从对象库中拖放对象到每个场景中，并使用Attributes inspector配置对象和界面之间的切换。

![xcode4_9](/images/xcode4_9.png)

你的主视图可能包含一个表格，表格中有多个条目，每一个条都有一个对应的详情场景来提供条目的具体信息。导航控制器提供了返回到主视图的返回按钮.

![xcode4_10](/images/xcode4_10.png)

### 连接代码和界面对象 [Connecting Objects to Code](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/ConnectingObjectstoCode.html#//apple_ref/doc/uid/TP40010215-CH44-SW1)
***

通过编写代码来实现界面对象的行为。代码通过动作和outlet连接来与界面对象沟通。

创建一个动作连接，控件就可以给代码发送消息了。控件是一种用户操作时产生即时动作或视觉效果的界面元素。例如，当用户点击一个按钮时，按钮会给代码发送一个动作消息来执行相应的动作。文本框、滑动条和开关都是iOS中常用的控件；复选框、滚动条以及文本框是Mac OS中常用的控件。

当您需要从代码给界面对象发送消息时，可创建一个outlet连接。对象可以是控件，也可以是storyboard 或 xib文件中定义的其他对象，例如一个标签、进度指示器或是地图视图。如果代码决定一个按钮需要消失，那么代码可以通过outlet发送消息告知按钮应当隐藏。


#### 通过控制器给代码发送消息 *Sending Action Messages from a Control to Your Code*

当用户点击控件并与之进行交互时，控件就会给代码发送消息来执行特定的动作。配置控件给代码发送动作信息的最简单方式是按下Control键，并用鼠标从Interface Builder中将控件拖到工程的执行文件中。

当Interface Builder在标准编辑器面板中打开时，选中你想要配置的控件，并点击辅助编辑器按钮打开项目的实现文件。

按下Control键，并用鼠标从Interface Builder中将控件拖到工程的执行文件中（图中辅助编辑器展示了Warrior按钮的视图控制器的执行文件），Xcode会提示你在代码的哪个位置插入动作方法。

![xcode4_11](/images/xcode4_11.png)

松开鼠标后，辅助编辑器会弹出一个Connection菜单，你可以输入动作方法的名称（下图中方法名称为chooseWarrior），然后点击连接。

![xcode4_12](/images/xcode4_12.png)

在实现文件里，Xcode为新方法插入了一个骨骼动画定义，如下所示。IBAction返回类型是一个特殊的关键字，表示这个实例方法可以连接到storyboard或xib文件。Xcode同时会配置控件，从而在选中事件发生时调用该方法。因此，只要控件收到一个动作信息，这个方法就会被调用。

![xcode4_13](/images/xcode4_13.png)

在这个骨骼动画定义中，你可以添加动作方法的源码。控件由系统激活，不过由你实现其行为。你在下面的图片中，当用户点击Warrior按钮时，这个动作方法会启动一个新游戏。

![xcode4_14](/images/xcode4_14.png)

#### 通过Outlet给界面元素发送消息 *Sending Messages to a User Interface Object Through an Outlet*
***

要通过代码给用户界面元素发送消息（比如通知标签展示文本字符串，通知按钮展示或者隐藏），你需要将界面元素和代码中的Outlet连接起来。最简单的方法是Control-点击-拖动画布上的UI对象到实现文件或头文件中。例如，要在试图控制器中创建一个outlet，并将其和按钮连接，你需要按下Control键并拖动IB中的按钮，将其放到辅助编辑器中视图控制器的实现文件中。Xcode会提示你在哪里插入是合适。

![xcode4_15](/images/xcode4_15.png)

释放Control拖动后，辅助编辑器会显示一个Connection菜单，选择Outlet，然后输入Outlet的名字（下图中Outlet的名字是warriorButton），点击Connect即可。

![xcode4_16](/images/xcode4_16.png)

Interface Builder会将Outlet的声明添加到类中（Outlet被定义为IBOutlet属性，IBOutlet关键字会告知Xcode该属性可以被连接到storyboard或xib文件中）

![xcode4_17](/images/xcode4_17.png)

### 适应不同的屏幕大小 [Building for Multiple Screen Sizes](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/BuildingforMultipleScreenSizes.html#//apple_ref/doc/uid/TP40010215-CH45-SW1)

#### 使用Size Classes类来适应不同的屏幕尺寸和设备持有方向 *Using Size Classes*

Size Classes 可以让你用一个storyboard来应对不同尺寸的屏幕。你需要建立一个界面，使得它可以在多数设备上运行，当屏幕大小改变时，只需更改需要变化的对象即可。

Size Classes会规定高和宽的一个相对的显示空间大小，这个大小可以是compact（紧凑型）或regular（常规型）。一般来说，iPhone竖屏时宽度是compact，横屏时高度是compact。iPhone竖屏时高度是regular，对于iPad，宽和高都是regular。具体的点数并不重要，相对的空间是重要的。

因为多数界面的显示对compact或regular选择都是一样的，因此还有一个额外的size class --any。你可以把compact和regular下一样的界面设为any，对于那些需要改变的再另外指出。Size Classes已知属性包括：

* 约束的常量
* 表明视图层次是否包含约束的布尔值
* 文本标签、文本域、文本视图或者按钮上的字体。

改变这些属性会导致界面的变化：

* 改变视图的大小或位置
* 添加或删除视图
* 添加或删除约束
* 改变文本标签、文本域、文本视图或者按钮上的字体。

需要注意的是，如果一个视图或布局约束在当前的size class下是不可用状态，也就是没有被装载到当前的size class中，这并不意味着该视图和布局约束的实例不存在，而是在它们出现时就已经被实例化了。无论哪种size class引用该视图或布局约束都会得到一个有效的对象。Xcode中的视图对象（不论是按钮还是图片，它们都是视图对象）都不会在界面层面有父视图对象，所以如果你卸载了一个视图，那么Xcode会相应的卸载掉与该视图相关的所有布局约束。

要为你的storyboard启用size classes，需要先在项目导航器中选中storyboard文件，然后在canvas面板的文件查看器那一栏的Use Size Classes复选框上打对勾。Xcode会询问你是否转换文件。打开size classes的同时会开启Auto Layout。

![xcode4_18](/images/xcode4_18.png)

启用size classes后，Xcode将以正方形在画布上展示所有顶层视图控制器。画布底部中心位置还有一个size classes的控件，该控件显示了当前size classes的宽高设置。在该示例中，它是any/any.

![xcode4_19](/images/xcode4_19.png)

如果要更改size classes，可点击下面的size classes控件，在弹出的菜单中移动鼠标，直到选中你想要的size classes为止。

![xcode4_20](/images/xcode4_20.png)

当你对size classes做出调整后，试图控制器的大小会相应改变，同时底栏也会变成蓝色，以提示你不在any/any的模式。

![xcode4_21](/images/xcode4_21.png)

你在一个特定size class中对约束、视图和字体做出的更改都仅限于该s类。要删除一个约束或视图，请选中它然后按下Command+Delete组合键。关闭一个视图后，你往往希望关闭与它相关的所有约束。

#### 界面元素布局的自动调整和定位 *Using Auto Layout for Automatic Resizing and Positioning*

自动布局可以帮你适应不同的窗口尺寸、屏幕尺寸以及设备持有方向。您可以通过给视图对象添加关系约束来实现。例如，你可以将一个图像在 storyboard场景中水平居中，当用户旋转设备时，图像会自动在新的布局中保持水平居中。

通过Auto Layout 约束来管理布局，界面中的元素会在以下情形中自动改变大小和位置：

* 用户改变了设备朝向
* 用户在Mac应用中改变了窗口大小
* 内容尺寸改变（例如字符串长度改变）

按下Control键并在两个界面对象间进行拖动，Interface Builder会弹出一个适当的约束列表，从列表中选择其中一项即可为项目添加约束。下图展示了从主logo视图拖放对象至控制器主视图的结果。弹出菜单显示了image view与容器间的两种约束选项。"Top Space to Container"是指图像视图与容器顶部之间的高度约束，另外一个约束定义了容器中图像水平居中。

![xcode4_22](/images/xcode4_22.png)

要查看一个对象的限制，可从大纲视图中选中该对象，或者在画布上选中该对象，出现的绿色实线则代表对象的约束，你可以点击尺寸查看器来查看约束列表。
![xcode4_23](/images/xcode4_23.png)

约束部分顶部形象化地展示了选中对象的约束类型，每条水平或者竖直的绿色实线表示一条或多条该类型约束。选择一条或多条实线可以筛选出符合该类型的约束列表。

![xcode4_24](/images/xcode4_24.png)

你可以在画布上选中约束，或者在Size inspector中双击约束来查看和编辑约束，再或者可以双击约束调出弹出编辑器来更改最常用的约束属性。

![xcode4_25](/images/xcode4_25.png)

还有更多的方法可以添加和编辑约束，包括使用底栏的按钮
![xcode4_26](/images/xcode4_26.png)

### 查看对象的文档 [Viewing Object Documentation](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/LookingupObjectDocumentation.html#//apple_ref/doc/uid/TP40010215-CH46-SW1)
***

您可以在Interface Builder中查看界面对象简略的类参考文档，而无需离开Interface Builder。

在文件打开的状态，点击按钮打开实用工具区，然后在检查器一栏选中Quick Help按钮。然后在Interface Builder点击你想要的对象的信息，文档会出现在工具区的检查器窗口中。

![xcode4_27](/images/xcode4_27.png)

如果要查看完整的详细文档，你需要点击 Quick Help中参考文档的标题，详细的参考文档会在新的文档查看窗口中打开。你还可以查看相应的编程指南、示例代码和其他相关文档。

如果要查看设置选项的更多信息，你需要将鼠标移动到该选项的上面，然后就会弹出一个帮助标签。

![xcode4_28](/images/xcode4_28.png)

## 预览您的用户界面 [Previewing Your User Interface](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/PreviewingYourUserInterface.html#//apple_ref/doc/uid/TP40010215-CH47-SW1)
***

使用内置的预览辅助编辑器可以预览您的用户界面在不同设备和使用不同语言，而不用编译您的应用程序。

![xcode4_29](/images/xcode4_29.png)

## 创建和绘制自定义的视图类 [Creating and Rendering Custom View Classes](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/CreatingandRenderingCustomViewClasses.html#//apple_ref/doc/uid/TP40010215-CH48-SW1)
***

你可以把自定义的视图类在设计时使用在界面生成器。您还可以添加属性的自定义视图类属性检查器。

![xcode4_30](/images/xcode4_30.png)

## 使用Interface Builder获得帮助 [Finding Help for Interface Builder](https://developer.apple.com/library/mac/documentation/ToolsLanguages/Conceptual/Xcode_Overview/FindingHelpforInterfaceBuilder.html#//apple_ref/doc/uid/TP40010215-CH49-SW1)
***

Xcode中提供了Interface Builder常见操作的详细步骤帮助。在Interface Builder画布中任意位置按住Control然后点击鼠标，就会出现一个菜单，里面列出了常用操作，选择 Show All Help Topics 就可以显示源码编辑器的所有帮助文章。

![xcode4_31](/images/xcode4_31.png)

因为Control-click这个操作在Interface Builder中用来创建连接，因此你必须在画布上执行Control点击来调出包含帮助文章列表的快捷菜单，而不是点击用户界面中的任意对象。

选中一个主题，帮助文章就会显示在Xcode文档查看器中。

![xcode4_32](/images/xcode4_32.png)
