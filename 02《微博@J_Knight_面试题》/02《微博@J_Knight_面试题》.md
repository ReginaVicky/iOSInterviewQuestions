# iOSInterviewQuestion
## 微博@J_Knight_面试题（附答案）

- 02《微博@J_Knight_面试题》，面试题来源是微博[@J_Knight_](https://weibo.com/1929625262/)的这篇博文：[《2017年5月iOS招人心得（附面试题）》](https://knightsj.github.io/2017/06/08/2017年5月iOS招人心得（附面试题）/)，其中共54题；
- 如有纰漏，请向微博[@爱吃兔兔的胡萝卜吖](https://weibo.com/6447187962/)反馈。


# 索引

1.[为什么说Objective-C是一门动态的语言？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#1为什么说objective-c是一门动态的语言)

2.[讲一下MVC和MVVM，MVP？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#2讲一下mvc和mvvmmvp)

3.[为什么代理要用weak？代理的delegate和dataSource有什么区别？block和代理的区别?](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#3为什么代理要用weak代理的delegate和datasource有什么区别block和代理的区别)

4.[属性的实质是什么？包括哪几个部分？属性默认的关键字都有哪些？@dynamic关键字和@synthesize关键字是用来做什么的？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#4属性的实质是什么包括哪几个部分属性默认的关键字都有哪些dynamic关键字和synthesize关键字是用来做什么的)

5.[属性的默认关键字是什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#5属性的默认关键字是什么)

6.[NSString为什么要用copy关键字，如果用strong会有什么问题？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#6nsstring为什么要用copy关键字如果用strong会有什么问题)

7.[如何令自己所写的对象具有拷贝功能?](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#7如何令自己所写的对象具有拷贝功能)

8.[可变集合类和不可变集合类的copy和mutablecopy有什么区别？如果是集合是内容复制的话，集合里面的元素也是内容复制么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#8可变集合类-和-不可变集合类的-copy-和-mutablecopy有什么区别如果是集合是内容复制的话集合里面的元素也是内容复制么)

9.[为什么IBOutlet修饰的UIView也适用weak关键字？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#9为什么iboutlet修饰的uiview也适用weak关键字)

10.[nonatomic和atomic的区别？atomic是绝对的线程安全么？为什么？如果不是，那应该如何实现？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#10nonatomic和atomic的区别atomic是绝对的线程安全么为什么如果不是那应该如何实现)

11.[UICollectionView自定义layout如何实现？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#11uicollectionview自定义layout如何实现)

12.[用StoryBoard开发界面有什么弊端？如何避免？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#12用storyboard开发界面有什么弊端如何避免)

13.[进程和线程的区别？同步异步的区别？并行和并发的区别？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#13进程和线程的区别同步异步的区别并行和并发的区别)

14.[线程间通信？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#14线程间通信)

15.[GCD的一些常用的函数？（group，barrier，信号量，线程同步）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#15gcd的一些常用的函数groupbarrier信号量线程同步)

16.[如何使用队列来避免资源抢夺？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#16如何使用队列来避免资源抢夺)

17.[数据持久化的几个方案（fmdb用没用过）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#17数据持久化的几个方案fmdb用没用过)

18.[说一下AppDelegate的几个方法？从后台到前台调用了哪些方法？第一次启动调用了哪些方法？从前台到后台调用了哪些方法？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#18说一下appdelegate的几个方法从后台到前台调用了哪些方法第一次启动调用了哪些方法从前台到后台调用了哪些方法)

19.[NSCache优于NSDictionary的几点？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#19nscache优于nsdictionary的几点)

20.[知不知道DesignatedInitializer？使用它的时候有什么需要注意的问题？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#20知不知道designated-initializer使用它的时候有什么需要注意的问题)

21.[实现description方法能取到什么效果？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#21实现description方法能取到什么效果)

22.[objc使用什么机制管理对象内存？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#22objc使用什么机制管理对象内存)

23.[block的实质是什么？一共有几种block？都是什么情况下生成的？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#23block的实质是什么一共有几种block都是什么情况下生成的)

24.[为什么在默认情况下无法修改被block捕获的变量？__block都做了什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#24为什么在默认情况下无法修改被block捕获的变量-__block都做了什么)

25.[模拟一下循环引用的一个情况？block实现界面反向传值如何实现？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#25模拟一下循环引用的一个情况block实现界面反向传值如何实现)

26.[objc在向一个对象发送消息时，发生了什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#26objc在向一个对象发送消息时发生了什么)

27.[什么时候会报unrecognizedselector错误？iOS有哪些机制来避免走到这一步？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#27什么时候会报unrecognized-selector错误ios有哪些机制来避免走到这一步)

28.[能否向编译后得到的类中增加实例变量？能否向运行时创建的类中添加实例变量？为什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#28能否向编译后得到的类中增加实例变量能否向运行时创建的类中添加实例变量为什么)

29.[runtime如何实现weak变量的自动置nil？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#29runtime如何实现weak变量的自动置nil)

30.[给类添加一个属性后，在类结构体里哪些元素会发生变化？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#30给类添加一个属性后在类结构体里哪些元素会发生变化)

31.[runloop是来做什么的？runloop和线程有什么关系？主线程默认开启了runloop么？子线程呢？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#31runloop是来做什么的runloop和线程有什么关系主线程默认开启了runloop么子线程呢)

32.[runloop的mode是用来做什么的？有几种mode？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#32runloop的mode是用来做什么的有几种mode)

33.[为什么把NSTimer对象以NSDefaultRunLoopMode（kCFRunLoopDefaultMode）添加到主运行循环以后，滑动scrollview的时候NSTimer却不动了？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#33为什么把nstimer对象以nsdefaultrunloopmodekcfrunloopdefaultmode添加到主运行循环以后滑动scrollview的时候nstimer却不动了)

34.[苹果是如何实现Autorelease Pool的？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#34苹果是如何实现autorelease-pool的)

35.[isa指针？（对象的isa，类对象的isa，元类的isa都要说）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#35isa指针对象的isa类对象的isa元类的isa都要说)

36.[类方法和实例方法有什么区别？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#36类方法和实例方法有什么区别)

37.[介绍一下分类，能用分类做什么？内部是如何实现的？它为什么会覆盖掉原来的方法？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#37介绍一下分类能用分类做什么内部是如何实现的它为什么会覆盖掉原来的方法)

38.[运行时能增加成员变量么？能增加属性么？如果能，如何增加？如果不能，为什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#38运行时能增加成员变量么能增加属性么如果能如何增加如果不能为什么)

39.[objc中向一个nil对象发送消息将会发生什么？（返回值是对象，是标量，结构体）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#39objc中向一个nil对象发送消息将会发生什么返回值是对象是标量结构体)

40.[UITableview的优化方法（缓存高度，异步绘制，减少层级，hide，避免离屏渲染](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#40uitableview的优化方法缓存高度异步绘制减少层级hide避免离屏渲染)

41.[有没有用过运行时，用它都能做什么？（交换方法，创建类，给新创建的类增加方法，改变isa指针）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#41有没有用过运行时用它都能做什么交换方法创建类给新创建的类增加方法改变isa指针)

42.[看过哪些第三方框架的源码？都是如何实现的？（如果没有，问一下多图下载的设计）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#42看过哪些第三方框架的源码都是如何实现的如果没有问一下多图下载的设计)

43.[SDWebImage的缓存策略？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#43sdwebimage的缓存策略)

44.[AFN为什么添加一条常驻线程？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#44afn为什么添加一条常驻线程)

45.[KVO的使用？实现原理？（为什么要创建子类来实现）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#45kvo的使用实现原理为什么要创建子类来实现)

46.[KVC的使用？实现原理？（KVC拿到key以后，是如何赋值的？知不知道集合操作符，能不能访问私有属性，能不能直接访问_ivar）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#46kvc的使用实现原理kvc拿到key以后是如何赋值的知不知道集合操作符能不能访问私有属性能不能直接访问_ivar)

47.[有已经上线的项目么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#47有已经上线的项目么)

48.[项目里哪个部分是你完成的？（找一个亮点问一下如何实现的）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#48项目里哪个部分是你完成的找一个亮点问一下如何实现的)

49.[开发过程中遇到过什么困难，是如何解决的？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#49开发过程中遇到过什么困难是如何解决的)

50.[遇到一个问题完全不能理解的时候，是如何帮助自己理解的？举个例子？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#50遇到一个问题完全不能理解的时候是如何帮助自己理解的举个例子)

51.[有看书的习惯么？最近看的一本是什么书？有什么心得？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#51有看书的习惯么最近看的一本是什么书有什么心得)

52.[有没有使用一些笔记软件？会在多平台同步以及多渠道采集么？（如果没有，问一下是如何复习知识的）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#52有没有使用一些笔记软件会在多平台同步以及多渠道采集么如果没有问一下是如何复习知识的)

53.[有没有使用清单类，日历类的软件？（如果没有，问一下是如何安排，计划任务的）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#53有没有使用清单类日历类的软件如果没有问一下是如何安排计划任务的)

54.[平常看博客么？有没有自己写过？（如果写，有哪些收获？如果没有写，问一下不写的原因）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/02《微博%40J_Knight_面试题》/02《微博%40J_Knight_面试题》.md#54平常看博客么有没有自己写过如果写有哪些收获如果没有写问一下不写的原因)


## 1.为什么说Objective-C是一门动态的语言？

- 首先动态类型语言和静态类型语言
    * 动态类型语言
        * 动态类型语言是指在运行期间才去做数据类型检查的语言，也就是说，在用动态类型的语言编程时，永远也不用给任何变量指定数据类型，该语言会在你第一次赋值给变量时，在内部将数据类型记录下来。
    * 静态类型语言
        * 静态类型语言与动态类型语言刚好相反，它的数据类型是在编译其间检查的，也就是说在写程序时要声明所有变量的数据类型，C/C++是静态类型语言的典型代表，其他的静态类型语言还有C#、JAVA等。
- oc具有相当多的动态特性，表现在三个方面：动态类型、动态绑定、动态加载。之所以叫做动态，是因为必须到运行时才会做一些事情。
    * 动态类型：即运行时再决定对象的类型。这类动态类型在日常应用中非常常见。简单说就是id类型。实际上静态类型因为其固定性和可预知性而使用的非常广泛，静态类型是请类型，而动态类型属于弱类型。运行时决定接受者。
    * 动态绑定：基于动态类型，在某个实例对象被确定后，起类型就被确定了。该对象的属性和响应的消息也被完全确定，这就是动态绑定
    * 动态加载：根据需求加载所需要的资源，这点很容易理解，对于ios开发来说，基本就是根据不同的急性左适配。最经典的例子就是在Retina设备上加载@2X的图片，而在老一些的普通设备上加载原图。随着Retina iPad的推出，和之后可能的Retina Mac的出现，这个特性相信会被越来越多的使用。让程序在运行时添加代码块以及其他资源。用户可以根据需要加载一些课指向代码和资源，而不是在启动时就加载所有组件。可执行代码中可以含有和程序运行时整合的新类。

## 2.讲一下MVC和MVVM，MVP？

- mvc
    * model-view-controller(模型-视图-控制器)；
    * model（模型）：视图类所需要的数据；model模型对象，封装了应用程序的数据，并定义操作该数据的逻辑和运算{网上很多介绍都很官方，不好理解}，用户在view视图中创建的数据和修改数据的操作通过控制器（controller）传达给model，来修改和创建数据。当有网络请求或本地修改数据时，通知控制器，控制器来对视图进行更新。model的处理任务是最多的，因为model需要处理数据库。model返回的数据没有格式限制，这样就可以为多个相似的视图提供数据，相应的也减少了不少代码量。
    * view（视图）：构建UI的类；view视图，是绘制出来的用户可以看见及操作的视图，主要用来显示model中的数据，并且数据可被编辑，view和model通常都是分离开的。view的控件都是UIView的子类，通过控制器整体显示在同一个界面，控件的响应通过委托代理模式交给controller实现。
    * controller（控制器）：连接视图类和模型类，任务是使数据显示在屏幕上。controller控制器，相当于媒介，能把一个视图和多个model或一个model和多个视图联系起来，通过controller视图能知道模型对象的改变（通知），反之亦然。控制器能够控制界面的流程以及程序的生命周期，控制器对象解释在视图对象中进行的用户操作，并将新的或更改过的数据传达给模型对象。模型对象更改时，一个控制器对象会将新的模型数据传达给视图对象，以便视图对象可以显示它。
    ![image](https://upload-images.jianshu.io/upload_images/2180450-3617e71d0979af37.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

- mvp
    * Model-View-Presenter
    * Model：与MVC中的model没有太大的区别。主要提供数据的存储功能，一般都是用来封装网络获取的json数据的集合。Presenter通过调用Model进行对象交互。
    * View：这里的View与MVC中的V又有一些小差别，这个View可以是viewcontroller、view等控件。Presenter通过向View传model数据进行交互。
    * Presenter（中介）：Presenter：作为model和view的中间人，从model层获取数据之后传给view，使得View和model没有耦合。在MVP里，Presenter完全把Model和View进行了分离，主要的程序逻辑在Presenter里实现。而且，Presenter与具体的View是没有直接关联的，而是通过定义好的接口进行交互，从而使得在变更View时候可以保持Presenter的不变，即重用！
    * mvp的优点：
        * 模型与视图完全分离，我们可以修改视图而不影响模型；
        * 可以更高效地使用模型，因为所有的交互都发生在一个地方——Presenter内部；
        * 我们可以将一个Presenter用于多个视图，而不需要改变Presenter的逻辑。这个特性非常的有用，因为视图的变化总是比模型的变化频繁；
        * 如果我们把逻辑放在Presenter中，那么我们就可以脱离用户接口来测试这些逻辑（单元测试）。

    ![image](https://upload-images.jianshu.io/upload_images/2180450-db9f5c59b28bf719.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

- mvvm
    * Model-View-ViewModel：（模型－视图－视图模型）
    * Model：与MVC中的model没有太大的区别。主要提供数据的存储功能，一般都是用来封装网络获取的json数据的集合。
    * View：这里的View与MVC中的V又有一些小差别，这个View可以是viewcontroller、view等控件。
    * ViewModel：它是View的抽象，负责View与Model之间信息转换，将View的Command传送到Model；View绑定到ViewModel，然后执行一些命令在向它请求一个动作。而反过来，ViewModel跟Model通讯，告诉它更新来响应UI。这样便使得为应用构建UI非常的容易。往一个应用程序上贴一个界面越容易，外观设计师就越容易使用Blend来创建一个漂亮的界面。同时，当UI和功能越来越松耦合的时候，功能的可测试性就越来越强。
    * 一般放viewmodel里的数据：
    * mvvm的优点：
        * 提高可维护性。解决了MVP大量的手动View和Model同步的问题，提供双向绑定机制。提高了代码的可维护性。
        * 简化测试。因为同步逻辑是交由Binder做的，View跟着Model同时变更，所以只需要保证Model的正确性，View就正确。大大减少了对View同步更新的测试。

![image](https://upload-images.jianshu.io/upload_images/2180450-72ff6480e1fdffb7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

## 3.为什么代理要用weak？代理的delegate和dataSource有什么区别？block和代理的区别?

- 为什么代理要用weak
    * 防止循环引用，UITableViewController内部有一个强指针tableView属性，
tableView指针指向一个UITableView，UITableView内部有一个强指针subviews属性，指向一个装着UITableView全部的子控件的强指针数组，数组中又有强指针指向UITableView中存在的子控件。tableView内部有一个指针delegate，tableView的delegate就是控制器本身，二者相互引用，因此必须有一个对象是弱指针，所以delegate是weak。
- 代理的delegate和dataSource有什么区别
    * delegate：代理，告诉使用者之前的view有什么方法可以供我调用。
    * dataSource：数据源，告诉使用者之前的view中都有什么东西，有什么属性啊，属性的值都是多少，是只关于数据的东西。
- block和代理的区别
    * 代理回调更面向过程，block更面向结果。
    * 如果需要在执行的不同步骤时被通知，你就要使用代理。
    * 如果只需要请求的消息或者失败的详情，应该使用block。
    * block更适合与状态无关的操作，比如被告知某些结果，block之间是不会相互影响的。
    * 但是代理更像一个生产流水线，每个回调方法是生产线上的一个处理步骤，一个回调的变动可能会引起另一个回调的变动。
    * 要是一个对象有超过一个的不同事件，应该使用代理。
    * 一个对象只有一个代理，要是某个对象是个单例对象，就不能使用代理。
    * 要是一个对象调用方法需要返回一些额外的信息，就可能需要使用代理。


## 4.属性的实质是什么？包括哪几个部分？属性默认的关键字都有哪些？@dynamic关键字和@synthesize关键字是用来做什么的？

-属性的实质：
    * 公式表达：ivar + getter + setter 。 @property其实就是在编译阶段又编译器为我们自动生成ivar成员变量的getter和setter方法。我们在声明一个属性的时候，编译器都做了什么：没次增加一个属性，系统都会在ivar_list中添加一个成员变量的描述。在method_list中添加setter和getter方法的描述。在prop_list中增加一个属性的描述，计算该属性在对象中的偏移量，然后给出setter和getter方法对应的实现。在setter方法中从偏移量的位置开始赋值，在getter方法中从偏移量开始取值。为了能够读取正确的字节数，系统对象偏移量的指针类型进行了类型强转。
- 包括那几个部分
    * 
- 属性默认的关键字都有哪些
- @dynamic关键字和@synthesize关键字是用来做什么的
    * @property有两个对应的词，一个是@synthesis一个是@dynamic。若两者都没有写，默认的就是：
    * @syntheszie var = _var；
    * @synthesis的语义是如果你没有手动实现setter和getter方法，那么编译器会自动为你加上这两个方法
    * @dynamic告诉编译器：属性的setter和getter方法由开发者自己实现，不需要自动生成。（对于readonly的属性只需提供getter即可）加入一个属性被声明为@dynamic var；
    * 然后你也没有提供@setter和@getter方法，可以通过编译，但是运行的时候，程序运行至
instance.var = someVar会因为缺少setter方法而crash。同样如果缺失getter方法，程序运行至someVar = instance.var时导致crash。



## 5.属性的默认关键字是什么？

- 属性可以拥有的特质分为四类:

    * 原子性--- nonatomic 特质，默认的是atomic
    
        在默认情况下，由编译器合成的方法会通过锁定机制确保其原子性(atomicity)。如果属性具备 nonatomic 特质，则不使用自旋锁。请注意，尽管没有名为“atomic”的特质(如果某属性不具备 nonatomic 特质，那它就是“原子的” ( atomic) )，但是仍然可以在属性特质中写明这一点，编译器不会报错。若是自己定义存取方法，那么就应该遵从与属性特质相符的原子性。

    * 读/写权限---readwrite(读写)、readonly (只读)，默认的是readwrite

    * 内存管理语义---assign、strong、 weak、unsafe_unretained、copy，默认的是assign

    * 方法名---getter=<name> 、setter=<name>
        * getter=<name>的样式：
```
@property (nonatomic, getter=isOn) BOOL on;
```
        
- - - setter=<name>一般用在特殊的情境下，比如：
    
    在数据反序列化、转模型的过程中，服务器返回的字段如果以 init 开头，所以你需要定义一个 init 开头的属性，但默认生成的 setter 与 getter 方法也会以 init 开头，而编译器会把所有以 init 开头的方法当成初始化方法，而初始化方法只能返回 self 类型，因此编译器会报错。

这时你就可以使用下面的方式来避免编译器报错：

```
@property(nonatomic, strong, getter=p_initBy, setter=setP_initBy:)NSString *initBy;
```
另外也可以用关键字进行特殊说明，来避免编译器报错：

```
@property(nonatomic, readwrite, copy, null_resettable) NSString *initBy;
- (NSString *)initBy __attribute__((objc_method_family(none)));
```

## 6.NSString为什么要用copy关键字，如果用strong会有什么问题？

- 因为父类指针可以指向子类对象,使用 copy 的目的是为了让本对象的属性不受外界影响,使用 copy 无论给我传入是一个可变对象还是不可对象,我本身持有的就是一个不可变的副本.
- 如果我们使用是 strong ,那么这个属性就有可能指向一个可变对象,如果这个可变对象在外部被修改了,那么会影响该属性.
- copy 此特质所表达的所属关系与 strong 类似。然而设置方法并不保留新值，而是将其“拷贝” (copy)。 当属性类型为 NSString 时，经常用此特质来保护其封装性，因为传递给设置方法的新值有可能指向一个 NSMutableString 类的实例。这个类是 NSString 的子类，表示一种可修改其值的字符串，此时若是不拷贝字符串，那么设置完属性之后，字符串的值就可能会在对象不知情的情况下遭人更改。所以，这时就要拷贝一份“不可变” (immutable)的字符串，确保对象中的字符串值不会无意间变动。只要实现属性所用的对象是“可变的” (mutable)，就应该在设置新属性值时拷贝一份。
- 举例说明：

定义一个以 strong 修饰的 array：

```
@property (nonatomic ,readwrite, strong) NSArray *array;
```
然后进行下面的操作：

```
NSArray *array = @[ @1, @2, @3, @4 ];
   NSMutableArray *mutableArray = [NSMutableArray arrayWithArray:array];
   
   self.array = mutableArray;
   [mutableArray removeAllObjects];;
   NSLog(@"%@",self.array);
   
   [mutableArray addObjectsFromArray:array];
   self.array = [mutableArray copy];
   [mutableArray removeAllObjects];;
   NSLog(@"%@",self.array);
```
打印结果如下所示：

```
2015-09-27 19:10:32.523 CYLArrayCopyDmo[10681:713670] (
)
2015-09-27 19:10:32.524 CYLArrayCopyDmo[10681:713670] (
   1,
   2,
   3,
   4
)
```
为了理解这种做法，首先要知道，两种情况：
- 对非集合类对象的 copy 与 mutableCopy 操作；
- 对集合类对象的 copy 与 mutableCopy 操作。

### 对非集合类对象的copy操作：
- 在非集合类对象中：对 immutable 对象进行 copy 操作，是指针复制，mutableCopy 操作时内容复制；对 mutable 对象进行 copy 和 mutableCopy 都是内容复制。用代码简单表示如下：

[immutableObject copy] // 浅复制
[immutableObject mutableCopy] //深复制
[mutableObject copy] //深复制
[mutableObject mutableCopy] //深复制
比如以下代码：

```
NSMutableString *string = [NSMutableString stringWithString:@"origin"];//copy
NSString *stringCopy = [string copy];
```
查看内存，会发现 string、stringCopy 内存地址都不一样，说明此时都是做内容拷贝、深拷贝。即使你进行如下操作：

```
[string appendString:@"origion!"]
```
stringCopy 的值也不会因此改变，但是如果不使用 copy，stringCopy 的值就会被改变。 集合类对象以此类推。 所以，

- 用 @property 声明 NSString、NSArray、NSDictionary 经常使用 copy 关键字，是因为他们有对应的可变类型：NSMutableString、NSMutableArray、NSMutableDictionary，他们之间可能进行赋值操作，为确保对象中的字符串值不会无意间变动，应该在设置新属性值时拷贝一份。

### 集合类对象的copy与mutableCopy

集合类对象是指 NSArray、NSDictionary、NSSet ... 之类的对象。下面先看集合类immutable对象使用 copy 和 mutableCopy 的一个例子：

```
NSArray *array = @[@[@"a", @"b"], @[@"c", @"d"]];
NSArray *copyArray = [array copy];
NSMutableArray *mCopyArray = [array mutableCopy];
```
查看内容，可以看到 copyArray 和 array 的地址是一样的，而 mCopyArray 和 array 的地址是不同的。说明 copy 操作进行了指针拷贝，mutableCopy 进行了内容拷贝。但需要强调的是：此处的内容拷贝，仅仅是拷贝 array 这个对象，array 集合内部的元素仍然是指针拷贝。这和上面的非集合 immutable 对象的拷贝还是挺相似的，那么mutable对象的拷贝会不会类似呢？我们继续往下，看 mutable 对象拷贝的例子：

```
NSMutableArray *array = [NSMutableArray arrayWithObjects:[NSMutableString stringWithString:@"a"],@"b",@"c",nil];
NSArray *copyArray = [array copy];
NSMutableArray *mCopyArray = [array mutableCopy];
```
查看内存，如我们所料，copyArray、mCopyArray和 array 的内存地址都不一样，说明 copyArray、mCopyArray 都对 array 进行了内容拷贝。同样，我们可以得出结论：

在集合类对象中，对 immutable 对象进行 copy，是指针复制， mutableCopy 是内容复制；对 mutable 对象进行 copy 和 mutableCopy 都是内容复制。但是：集合对象的内容复制仅限于对象本身，对象元素仍然是指针复制。用代码简单表示如下：

```
[immutableObject copy] // 浅复制
[immutableObject mutableCopy] //单层深复制
[mutableObject copy] //单层深复制
[mutableObject mutableCopy] //单层深复制
```
这个代码结论和非集合类的非常相似。

参考链接：[iOS 集合的深复制与浅复制](https://www.zybuluo.com/MicroCai/note/50592)


## 7.如何令自己所写的对象具有拷贝功能?

> 若想令自己所写的对象具有拷贝功能，则需实现 NSCopying 协议。如果自定义的对象分为可变版本与不可变版本，那么就要同时实现 NSCopying 与 NSMutableCopying 协议。
- 具体步骤：
    * 需声明该类遵从 NSCopying 协议
    * 实现 NSCopying 协议。该协议只有一个方法:

```
- (id)copyWithZone:(NSZone *)zone;
```
- 注意：一提到让自己的类用 copy 修饰符，我们总是想覆写copy方法，其实真正需要实现的却是 “copyWithZone” 方法。
- 以第一题的代码为例：

```
// .h文件
   // 修改完的代码

   typedef NS_ENUM(NSInteger, CYLSex) {
       CYLSexMan,
       CYLSexWoman
   };

   @interface CYLUser : NSObject<NSCopying>

   @property (nonatomic, readonly, copy) NSString *name;
   @property (nonatomic, readonly, assign) NSUInteger age;
   @property (nonatomic, readonly, assign) CYLSex sex;

   - (instancetype)initWithName:(NSString *)name age:(NSUInteger)age sex:(CYLSex)sex;
   + (instancetype)userWithName:(NSString *)name age:(NSUInteger)age sex:(CYLSex)sex;

   @end
```
然后实现协议中规定的方法：

```
- (id)copyWithZone:(NSZone *)zone {
	CYLUser *copy = [[[self class] allocWithZone:zone] 
		             initWithName:_name
 							      age:_age
						          sex:_sex];
	return copy;
}
```
但在实际的项目中，不可能这么简单，遇到更复杂一点，比如类对象中的数据结构可能并未在初始化方法中设置好，需要另行设置。举个例子，假如 CYLUser 中含有一个数组，与其他 CYLUser 对象建立或解除朋友关系的那些方法都需要操作这个数组。那么在这种情况下，你得把这个包含朋友对象的数组也一并拷贝过来。下面列出了实现此功能所需的全部代码:

```
// .h文件
// 以第一题《风格纠错题》里的代码为例

typedef NS_ENUM(NSInteger, CYLSex) {
    CYLSexMan,
    CYLSexWoman
};

@interface CYLUser : NSObject<NSCopying>

@property (nonatomic, readonly, copy) NSString *name;
@property (nonatomic, readonly, assign) NSUInteger age;
@property (nonatomic, readonly, assign) CYLSex sex;

- (instancetype)initWithName:(NSString *)name age:(NSUInteger)age sex:(CYLSex)sex;
+ (instancetype)userWithName:(NSString *)name age:(NSUInteger)age sex:(CYLSex)sex;
- (void)addFriend:(CYLUser *)user;
- (void)removeFriend:(CYLUser *)user;

@end
```
// .m文件

```
// .m
//

@implementation CYLUser {
   NSMutableSet *_friends;
}

- (void)setName:(NSString *)name {
   _name = [name copy];
}

- (instancetype)initWithName:(NSString *)name
                        age:(NSUInteger)age
                        sex:(CYLSex)sex {
   if(self = [super init]) {
       _name = [name copy];
       _age = age;
       _sex = sex;
       _friends = [[NSMutableSet alloc] init];
   }
   return self;
}

- (void)addFriend:(CYLUser *)user {
   [_friends addObject:user];
}

- (void)removeFriend:(CYLUser *)user {
   [_friends removeObject:user];
}

- (id)copyWithZone:(NSZone *)zone {
   CYLUser *copy = [[[self class] allocWithZone:zone]
                    initWithName:_name
                    age:_age
                    sex:_sex];
   copy->_friends = [_friends mutableCopy];
   return copy;
}

- (id)deepCopy {
   CYLUser *copy = [[[self class] alloc]
                    initWithName:_name
                    age:_age
                    sex:_sex];
   copy->_friends = [[NSMutableSet alloc] initWithSet:_friends
                                            copyItems:YES];
   return copy;
}

@end
```
以上做法能满足基本的需求，但是也有缺陷：
> 如果你所写的对象需要深拷贝，那么可考虑新增一个专门执行深拷贝的方法。

在例子中，存放朋友对象的 set 是用 “copyWithZone:” 方法来拷贝的，这种浅拷贝方式不会逐个复制 set 中的元素。若需要深拷贝的话，则可像下面这样，编写一个专供深拷贝所用的方法:

```
- (id)deepCopy {
   CYLUser *copy = [[[self class] alloc]
                    initWithName:_name
                    age:_age
                    sex:_sex];
   copy->_friends = [[NSMutableSet alloc] initWithSet:_friends
                                            copyItems:YES];
   return copy;
}
```

## 8.可变集合类 和 不可变集合类的 copy 和 mutablecopy有什么区别？如果是集合是内容复制的话，集合里面的元素也是内容复制么？

### 对非集合类对象的copy操作：
- 在非集合类对象中：对 immutable 对象进行 copy 操作，是指针复制，mutableCopy 操作时内容复制；对 mutable 对象进行 copy 和 mutableCopy 都是内容复制。用代码简单表示如下：

[immutableObject copy] // 浅复制
[immutableObject mutableCopy] //深复制
[mutableObject copy] //深复制
[mutableObject mutableCopy] //深复制
比如以下代码：

```
NSMutableString *string = [NSMutableString stringWithString:@"origin"];//copy
NSString *stringCopy = [string copy];
```
查看内存，会发现 string、stringCopy 内存地址都不一样，说明此时都是做内容拷贝、深拷贝。即使你进行如下操作：

```
[string appendString:@"origion!"]
```
stringCopy 的值也不会因此改变，但是如果不使用 copy，stringCopy 的值就会被改变。 集合类对象以此类推。 所以，

- 用 @property 声明 NSString、NSArray、NSDictionary 经常使用 copy 关键字，是因为他们有对应的可变类型：NSMutableString、NSMutableArray、NSMutableDictionary，他们之间可能进行赋值操作，为确保对象中的字符串值不会无意间变动，应该在设置新属性值时拷贝一份。

### 集合类对象的copy与mutableCopy

集合类对象是指 NSArray、NSDictionary、NSSet ... 之类的对象。下面先看集合类immutable对象使用 copy 和 mutableCopy 的一个例子：

```
NSArray *array = @[@[@"a", @"b"], @[@"c", @"d"]];
NSArray *copyArray = [array copy];
NSMutableArray *mCopyArray = [array mutableCopy];
```
查看内容，可以看到 copyArray 和 array 的地址是一样的，而 mCopyArray 和 array 的地址是不同的。说明 copy 操作进行了指针拷贝，mutableCopy 进行了内容拷贝。但需要强调的是：此处的内容拷贝，仅仅是拷贝 array 这个对象，array 集合内部的元素仍然是指针拷贝。这和上面的非集合 immutable 对象的拷贝还是挺相似的，那么mutable对象的拷贝会不会类似呢？我们继续往下，看 mutable 对象拷贝的例子：

```
NSMutableArray *array = [NSMutableArray arrayWithObjects:[NSMutableString stringWithString:@"a"],@"b",@"c",nil];
NSArray *copyArray = [array copy];
NSMutableArray *mCopyArray = [array mutableCopy];
```
查看内存，如我们所料，copyArray、mCopyArray和 array 的内存地址都不一样，说明 copyArray、mCopyArray 都对 array 进行了内容拷贝。同样，我们可以得出结论：

在集合类对象中，对 immutable 对象进行 copy，是指针复制， mutableCopy 是内容复制；对 mutable 对象进行 copy 和 mutableCopy 都是内容复制。但是：集合对象的内容复制仅限于对象本身，对象元素仍然是指针复制。用代码简单表示如下：

```
[immutableObject copy] // 浅复制
[immutableObject mutableCopy] //单层深复制
[mutableObject copy] //单层深复制
[mutableObject mutableCopy] //单层深复制
```
这个代码结论和非集合类的非常相似。

简而言之：
- 对不可变的非集合对象，copy是指针拷贝，mutablecopy是内容拷贝
- 对于可变的非集合对象，copy，mutablecopy都是内容拷贝
- 对不可变的数组、字典、集合等集合类对象，copy是指针拷贝，mutablecopy是内容拷贝
- 对于可变的数组、字典、集合等集合类对象，copy，mutablecopy都是内容拷贝

但是，对于集合对象的内容复制仅仅是对对象本身，但是对象的里面的元素还是指针复制。要想复制整个集合对象，就要用集合深复制的方法，有两种：

（1）使用initWithArray:copyItems:方法，将第二个参数设置为YES即可

```
NSDictionary shallowCopyDict = [[NSDictionary alloc] initWithDictionary:someDictionary copyItems:YES];
```
（2）将集合对象进行归档（archive）然后解归档（unarchive）：

```
NSArray *trueDeepCopyArray = [NSKeyedUnarchiver unarchiveObjectWithData:[NSKeyedArchiver archivedDataWithRootObject:oldArray]];
```


## 9.为什么IBOutlet修饰的UIView也适用weak关键字？

我们将控件拖到Storyboard上，相当于创建了一个对象，而这个对象是加到试图控制器的view上，存放在view的subviews数组中。即我们的控件对象是属于的view的，view对其子控件之前的关系是强引用。当我们使用Outlet属性的时候，这个Outlet属性是有view来进行强引用的。我们是在viewController中仅仅对其进行使用，没有必要拥有它，所以使用weak进行修饰。


## 10.nonatomic和atomic的区别？atomic是绝对的线程安全么？为什么？如果不是，那应该如何实现？



## 11.UICollectionView自定义layout如何实现？

> 在创建自定义的layout之前，你需要知道UICollectionViewFlowLayout提供的很多特性已经 经过优化以满足多种常用的layout。除非是如下情况，否则不建议自定义

- 你所想实现的外观并不是网格或者 line-based breaking 布局（items排成一行直到行满，再继续往下一行上去排，直到所有items都排列完成），或者必须要在多个方向上都可以滚动
- 需要频繁地改变所有 Cell的位置，以致于创建自定义layout比修改现有flow layout工作量更省

==记住：自定义最难的部分是确定布局中各item位置所需要的计算==

### 继承UICollectionViewLayout
- 继承UICollectionViewLayout之后只需要重载几个提供布局核心特性的方法，其他方法只需按情况重载即可，核心特性如下：
    * 指定可滚动内容区域的size
    * 为布局中的每个Cell及view提供属性对象
- layout对象需要用到datasource以创建collection view的layout对象，其通过layout自身的collectionView属性访问此datasource。需要注意的是，知道 layout过程中哪些信息可以从collection view中访问到，哪些不可以 是非常重要的。因为layout过程中，collection view 是无法获知各View的布局以及位置的。所以尽量避免通过 collection view获取除layout之外的信息。
> 深入理解布局过程

collection view完全通过你自定义的layout对象管理整个布局过程，如 collection view 首次布局或者resize的时候，会向布局对象获取相关信息。你也可以手动调用invalidateLayout方法以更新布局对象，此方法会强制生成新layout。（需要注意invalidateLayout与reloadData的区别，在移动，添加或者删除item的时候，需要摒弃原有布局，重新生成新的布局，使用invalidateLayout，而如果只是datasource中的数据有更新，这时需要使用reloadData）

layout过程中，如下方法提供了layout的基本信息，其他方法也会被调用，但如下这些方法总是按如下顺序调用的：

1 prepareLayout方法调用来为即将进行的layout作前期的计算

2 collectionViewContentSize方法基于初始计算，返回整体内容区域的size

3 layoutAttributesForElementsInRect:方法返回指定区域中cells和views的属性

![image](https://upload-images.jianshu.io/upload_images/268750-cd700e8158f38214.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

prepareLayout方法是为确定布局中各cell和view位置做计算，需要在此方法中算出足够的信息以供后续方法计算内容区域的整体size，collection view使用content size 以正确地配置scroll view。比如 content size 长宽均超过屏幕的话，水平与竖直方向的滚动都会被enable。基于当前滚动位置，collection view会调用 layoutAttributesForElementsInRect:方法以请求特定rect(有可能是也可能不是可见rect）中cell和view的属性。到此，core layout process已经结束了。

layout结束之后，cells和views的属性在你或者collection view invalidate布局之前都不会变，collection view可以在滚动的过程中自动invalidate 布局：用户滚动内容过程中，collection view调用layout的shouldInvalidateLayoutForBoundsChange:方法，如果返回值为YES则invalidate 布局。（但需要知道的是，invalidateLayout并不会马上触发layout update process,而是在下一个view更新周期中，collection view发现layout已经dirty才会去更新)

> 创建布局属性

自定义layout需要返回UICollectionViewLayoutAttributes类的对象，这些对象可以在很多不同方法中创建，但创建时间可以根据具体情况具体决定。如果collectionview未有数千的item,则prepare layout时创建会比在用户滚动过程中用到时再计算更可取，因为创建的这些属性可以缓存起来。如果计算所有属性并缓存起来所带来的性能消耗比请求时获取的消耗更大，则可请求时再创建相关属性对象。

创建UICollectionViewLayoutAttributes类对象新实例时，可以使用这样几个方法：layoutAttributesForCellWithIndexPath:，layoutAttributesForSupplementaryViewOfKind:withIndexPath:，layoutAttributesForDecorationViewOfKind:withIndexPath:，基于展示的view类型的不同，必须使用正确的类方法，因为collection view使用这些信息向datasource对象请求适当类型的view。使用错误的方法会引起collection view在错误的地方创建错误的view，你所希望呈现的layout就不会出现。

创建每个属性对象之后，将相应View的相关属性都设置上。最少要在layout中设置view的size和position。如果在你的布局中有view重叠了，需要正确配置zIndex属性以维持重叠views的一致的有序状态。其他属性可以让你控制cell或者view的可见性或者外观表现。如果标准属性类无法满足你的需要，可以继承并对其进行扩充以存储每个View的其他信息。继承layout属性时，需要实现属性的isEqual:方法因为collectionview需要使用这个方法。

> 给定矩形中的items的布局属性

layout processs的最后，collection view会调用你的layout对象的layoutAttributesForElementsInRect：方法。对一个大的可滚动的内容区域，collectionview可能只会请求当前可见的那部分区域中的所有items的属性。当然，这个方法需要支持获取任意rect中items的信息，因为有可能在插入及删除时需要做动画效果。

![image](https://upload-images.jianshu.io/upload_images/268750-30364131ff8a1720.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

layoutAttributesForElementsInRect：方法的实现需要遵循如下步骤：

1 遍历prepareLayout方法产生的数据以访问缓存的属性或者创建新的属性

2 检查每个item的frame以确定是否与layoutAttributesForElementsInRect:方法中指定rectangle有重叠部分

3 对每个重叠的item，添加一个对应的UICollectionViewLayoutAttributes对象到一个数组中

4 返回布局属性的数组给collection view

不仅要记住缓存layout信息能够带来性能提升，也要记住不断重复为cells创建新layout属性的计算代价是十分昂贵的，足以影响到app的性能。当collection view管理的items量很大时，采用在请求时创建layout属性的方式是十分合理的。

> 按需提供布局属性对象

collection view会在正常的layout 过程之外周期性地让你提供单个items的layout对象。比如为某item配置插入和删除动画时。自定义的layout通过如下方法提供这些信息：

layoutAttributesForItemAtIndexPath:

layoutAttributesForSupplementaryViewOfKind:atIndexPath:

layoutAttributesForDecorationViewOfKind:atIndexPath:

返回属性时，不能更新这些layout属性，如果需要改变layout信息，调用invalidateLayout，在接下来的layout周期中更新这些信息。上述方法中layoutAttributesForItemAtIndexPath：是所有自定义 layout都必须重载的方法，如果有supplementary view和decoration view可以分别重载下面两个方法。

> 可以通过self.collectionView.collectionViewLayout = [[MyCustomLayout alloc] init];方式也可以在storyboard文件中设置collection view 的class属性

### 让你的layout更优异

除了上述这些必须实现的方法，还有一些特性能够改善自定义layout的用户体验，实现这些属性是可选但推荐实现的。

> 通过 附加view 提供内容品质

supplementary views与Cells分离且有自己的layout属性，由Datasource提供，且其目的是为app主要内容增强信息。与cells一样，supplementary view也会经历重用的过程以最小化collection view使用的资源消耗。所以所有 supplementary view都需要继承UICollectionReusableView。

添加supplementary view到layout中的过程如下：

1 注册supplementary view到layout对象中，registerClass:forSupplementaryViewOfKind:withReuseIdentifier: or registerNib:forSupplementaryViewOfKind:withReuseIdentifier:

2 在datasource中实现collectionView:viewForSupplementaryElementOfKind:atIndexPath:,由于这些view是可重用的，调用dequeueReusableSupplementaryViewOfKind:withReuseIdentifier:forIndexPath:来获取可用的view

3 但为Cells创建一样为supplementary Views创建layout 属性对象

4 layoutAttributesForElementsInRect:方法中返回的属性数组中包含supplementary view的layout属性对象

5 实现layoutAttributesForSupplementaryViewOfKind:atIndexPath:方法为特定supplementary View返回属性对象

处理supplementaryview布局属性的过程和cell属性的过程一样，但不同的是supplementary view可以有很多种但只能有一种Cell。这是因为 supplementary view与它们是分离开的，是为了烘托主旨，所以每个supplementary view方法都会指明其各类以方便正确计算其特有的属性。

> 在layout中添加Decoration Views

Decoration Views是layout UI特征的有效点缀，与cell和supplementary view不同的是，它只做外观呈现用，所以与datasource无关。可以用来提供自定义背影，在Cells缝隙之间填充，甚至可以掩盖cell,它完全由layout对象控制。

在layout中添加Decoration view步骤如下：

1 用registerClass:forDecorationViewOfKind: or registerNib:forDecorationViewOfKind: method方法注册自定义的decoration view，但记住是在layout对象中注册

2 layout对象中layoutAttributesForElementsInRect:方法中为decoration view创建属性

3 实现layoutAttributesForDecorationViewOfKind:atIndexPath:方法并在请求时返回decoration view的布局属性

4 选择性地实现initialLayoutAttributesForAppearingDecorationElementOfKind:atIndexPath: 和 finalLayoutAttributesForDisappearingDecorationElementOfKind:atIndexPath:方法以处理出现和消失的动画，可参考下面的插入和删除动画部分

由于decoration view与cell和supplementary view的创建过程不同，注册class或者 nib即可，最多需要调用 一个initWithFrame:方法。但任何decoration view也需要是UICollectionReusableView子类，因为 也对其启用了回收机制。

> 插入和删除动画

插入及删除cell时collection view会询问layout对象提供一组初始化属性用于动画，同样，删除元素时会询问一组终值属性。

![image](https://upload-images.jianshu.io/upload_images/268750-44af6d2d9ef3b376.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

item插入时，layout对象提供正要被插入的item的初始化layout信息。在此例中，layout先将Cell的初始化位置设置到Collection view中间，并将其alpha通道设置为0，动画期间，此item会渐现并从中间移动到右下角。下面的代码描述了如何设置初始化信息及实现动画：

![image](https://upload-images.jianshu.io/upload_images/268750-a64cb521b2521b45.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

需要注意的是，上述代码会使得此item插入的时候对所有Cell都会添加此插入的动画，若只想对插入的item做插入动画，可以检查 index path是否与传入prepareForCollectionViewUpdates:方法的item的index path匹配，并只在有匹配到的时候才进行动画，否则只返回super initialLayoutAttributesForAppearingItemAtIndexPath:

delete动画与插入类似，提供正确的final 属性即可

> 提升layout的滚动体验

滚动的时候scrollview会根据当前的speed和减速状况决定最终会停在哪个偏移，当算出这个停留位置之后，其会调用 targetContentOffsetForProposedContentOffset:withScrollingVelocity:方法是否要改变这个位置，由于其是在滚动过程中调用此方法，所以自定义layout可以改变滚动的仪停留位置。

下图展示了调整滚动特性的效果

![image](https://upload-images.jianshu.io/upload_images/268750-9c00715d303bc260.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

假定collection view开始于（0，0），且用户向左侧滑，collection view计算出滚动原本会停下的位置，自定义layout可能会改变这个值以确保滚动停下的时候，某个item正好停留在可见区域正中间。这个新值会成为新的目标content offset，且会从targetContentOffsetForProposedContentOffset:withScrollingVelocity：方法返回。

注意：

1 items数较小（数百），或者items layout信息变化较小 时，可以在prepareLayout中创建并缓存layout信息

2 尽量不要继承UICollectionView

3 不要在layoutAttributesForElementsInRect：方法中调用uicollectionview的visiblecells方法，因为其实这个调用是转化成了向layout对象请求visible cells



## 12.用StoryBoard开发界面有什么弊端？如何避免？



## 13.进程和线程的区别？同步异步的区别？并行和并发的区别？

- 进程和线程的区别
    * 一个程序至少要有进程，一个进程至少要有一个线程
    * 进程：资源分配的最小独立单元，进程是具有一定独立功能的程序关于某个数据集合上的一次运行活动，进程是系统进行资源分配和调度的一个独立单位
    * 线程:进程下的一个分支，是进程的实体，是cpu调度和分派的基本单元，它使比进程更小的能独立运行的基本单位，线程自己基本不拥有系统资源，只拥有一点在运行中必不可少的资源呢，但是它可与同属一个进程的其他线程共享进程所拥有的全部资源
    * 进程和线程都是由操作系统所体会的程序运行的基本单元，系统利用该基本单元实现系统对应用的并发性
    * 进程和线程的主要差别在于它们是不同的操作系统资源管理方式，进程有独立的地址空间，一个进程崩溃后，在保护模式下不会对其它进程产生影响，而进程只是一个进程中的不同执行路径。线程有自己的堆栈和局部变量，但线程之间没有单独的地址空间，一个线程死掉就等于这个进程死掉，所以多进程的程序要比多线程的程序健壮，但在进程切换时，耗费资源较大，效率要差一些。
    * 但对于一些要求同时进行并且又要共享某些变量的并发操作，只能用线程，不能用进程

- 同步和异步、并发和并行的区别？

1、并发：在操作系统中，是指一个时间段中有几个程序都处于已启动运行到运行完毕之间，且这几个程序都是在同一个处理机上运行。其中两种并发关系分别是同步和互斥

2、同步：进程之间的关系不是相互排斥临界资源的关系，而是相互依赖的关系。进一步的说明：就是前一个进程的输出作为后一个进程的输入，当第一个进程没有输出时第二个进程必须等待。具有同步关系的一组并发进程相互发送的信息称为消息或事件。

3、互斥：进程间相互排斥的使用临界资源的现象，就叫互斥。

4、并行：在单处理器中多道程序设计系统中，进程被交替执行，表现出一种并发的外部特种；在多处理器系统中，进程不仅可以交替执行，而且可以重叠执行。在多处理器上的程序才可实现并行处理。从而可知，并行是针对多处理器而言的。并行是同时发生的多个并发事件，具有并发的含义，但并发不一定并行，也亦是说并发事件之间不一定要同一时刻发生。

5、异步：异步和同步是相对的，同步就是顺序执行，执行完一个再执行下一个，需要等待、协调运行。异步就是彼此独立,在等待某事件的过程中继续做自己的事，不需要等待这一事件完成后再工作。线程就是实现异步的一个方式。异步是让调用方法的主线程不需要同步等待另一线程的完成，从而可以让主线程干其它的事情。

6、串行和并行：串行是一次只能执行一个任务，并行是一次能执行多个任务；并行是CPU的多核芯同时执行多个任务  并发是单核CPU交替执行两个任务

7、同步异步关注的是消息通讯机制，所谓同步，就是在发出一个*调用*时，在没有得到结果之前，该*调用*就不返回。但是一旦调用返回，就得到返回值了。注意这个返回是指CUP返回执行的数据段部分，所以目前来看只是阻塞了CPU的数据段部分 并不耽误CPU干别的 所以即使是同步也不见得是阻塞模式。换句话说，就是由*调用者*主动等待这个*调用*的结果。而异步则是相反，*调用*在发出之后，这个调用就直接返回了，所以没有返回结果。换句话说，当一个异步过程调用发出后，调用者不会立刻得到结果。而是在*调用*发出后，*被调用者*通过状态、通知来通知调用者，或通过回调函数处理这个调用。典型的异步编程模型比如Node.js


## 14.线程间通信？



## 15.GCD的一些常用的函数？（group，barrier，信号量，线程同步）



## 16.如何使用队列来避免资源抢夺？



## 17.数据持久化的几个方案（fmdb用没用过）



## 18.说一下AppDelegate的几个方法？从后台到前台调用了哪些方法？第一次启动调用了哪些方法？从前台到后台调用了哪些方法？



## 19.NSCache优于NSDictionary的几点？



## 20.知不知道Designated Initializer？使用它的时候有什么需要注意的问题？



## 21.实现description方法能取到什么效果？



## 22.objc使用什么机制管理对象内存？

## 23.block的实质是什么？一共有几种block？都是什么情况下生成的？

## 24.为什么在默认情况下无法修改被block捕获的变量？ __block都做了什么？
## 25.模拟一下循环引用的一个情况？block实现界面反向传值如何实现？

## 26.objc在向一个对象发送消息时，发生了什么？

## 27.什么时候会报unrecognized selector错误？iOS有哪些机制来避免走到这一步？

## 28.能否向编译后得到的类中增加实例变量？能否向运行时创建的类中添加实例变量？为什么？

## 29.runtime如何实现weak变量的自动置nil？

- runtime 对注册的类， 会进行布局，对于 weak 对象会放入一个 hash 表中。 用 weak 指向的对象内存地址作为 key，当此对象的引用计数为0的时候会 dealloc，假如 weak 指向的对象内存地址是a，那么就会以a为键， 在这个 weak 表中搜索，找到所有以a为键的 weak 对象，从而设置为 nil。
- __weak引用的解除时间:
    * 对象的内存销毁时间表，分四个步骤：

```
// 对象的内存销毁时间表
// 根据 WWDC 2011, Session 322 (36分22秒)中发布的内存销毁时间表 

 1. 调用 -release ：引用计数变为零
     * 对象正在被销毁，生命周期即将结束.
     * 不能再有新的 __weak 弱引用， 否则将指向 nil.
     * 调用 [self dealloc] 
 2. 子类 调用 -dealloc
     * 继承关系中最底层的子类 在调用 -dealloc
     * 如果是 MRC 代码 则会手动释放实例变量们（iVars）
     * 继承关系中每一层的父类 都在调用 -dealloc
 3. NSObject 调 -dealloc
     * 只做一件事：调用 Objective-C runtime 中的 object_dispose() 方法
 4. 调用 object_dispose()
     * 为 C++ 的实例变量们（iVars）调用 destructors 
     * 为 ARC 状态下的 实例变量们（iVars） 调用 -release 
     * 解除所有使用 runtime Associate方法关联的对象
     * 解除所有 __weak 引用
     * 调用 free()
```
- 我们可以设计一个函数（伪代码）来表示上述机制：
- objc_storeWeak(&a, b)函数：
    * objc_storeWeak函数把第二个参数--赋值对象（b）的内存地址作为键值key，将第一个参数--weak修饰的属性变量（a）的内存地址（&a）作为value，注册到 weak 表中。如果第二个参数（b）为0（nil），那么把变量（a）的内存地址（&a）从weak表中删除，
    * 你可以把objc_storeWeak(&a, b)理解为：objc_storeWeak(value, key)，并且当key变nil，将value置nil。
    * 在b非nil时，a和b指向同一个内存地址，在b变nil时，a变nil。此时向a发送消息不会崩溃：在Objective-C中向nil发送消息是安全的。
    * 而如果a是由assign修饰的，则： 在b非nil时，a和b指向同一个内存地址，在b变nil时，a还是指向该内存地址，变野指针。此时向a发送消息极易崩溃。
    * 下面我们将基于objc_storeWeak(&a, b)函数，使用伪代码模拟“runtime如何实现weak属性”：

```
// 使用伪代码模拟：runtime如何实现weak属性
// http://weibo.com/luohanchenyilong/
// https://github.com/ChenYilong

 id obj1;
 objc_initWeak(&obj1, obj);
/*obj引用计数变为0，变量作用域结束*/
 objc_destroyWeak(&obj1);
```
- 下面对用到的两个方法objc_initWeak和objc_destroyWeak做下解释：
    * 总体说来，作用是： 通过objc_initWeak函数初始化“附有weak修饰符的变量（obj1）”，在变量作用域结束时通过objc_destoryWeak函数释放该变量（obj1）。
- 下面分别介绍下方法的内部实现：
    * objc_initWeak函数的实现是这样的：在将“附有weak修饰符的变量（obj1）”初始化为0（nil）后，会将“赋值对象”（obj）作为参数，调用objc_storeWeak函数。

```
obj1 = 0；
obj_storeWeak(&obj1, obj);
```
也就是说：weak 修饰的指针默认值是 nil

（在Objective-C中向nil发送消息是安全的）
然后obj_destroyWeak函数将0（nil）作为参数，调用objc_storeWeak函数。

objc_storeWeak(&obj1, 0);
- 前面的源代码与下列源代码相同。

```
// 使用伪代码模拟：runtime如何实现weak属性
// http://weibo.com/luohanchenyilong/
// https://github.com/ChenYilong

id obj1;
obj1 = 0;
objc_storeWeak(&obj1, obj);
/* ... obj的引用计数变为0，被置nil ... */
objc_storeWeak(&obj1, 0);
```
objc_storeWeak函数把第二个参数--赋值对象（obj）的内存地址作为键值，将第一个参数--weak修饰的属性变量（obj1）的内存地址注册到 weak 表中。如果第二个参数（obj）为0（nil），那么把变量（obj1）的地址从weak表中删除。

## 30.给类添加一个属性后，在类结构体里哪些元素会发生变化？

## 31.runloop是来做什么的？runloop和线程有什么关系？主线程默认开启了runloop么？子线程呢？

## 32.runloop的mode是用来做什么的？有几种mode？

- model主要是用来指定事件在运行循环中的优先级的，分为：
    * NSDefaultRunLoopMode（kCFRunLoopDefaultMode）：默认，空闲状态
    * UITrackingRunLoopMode：ScrollView滑动时
    * UIInitializationRunLoopMode：启动时
    * NSRunLoopCommonModes（kCFRunLoopCommonModes）：Mode集合
- 苹果公开提供的 Mode 有两个：
    * NSDefaultRunLoopMode（kCFRunLoopDefaultMode）
    * NSRunLoopCommonModes（kCFRunLoopCommonModes）

## 33.为什么把NSTimer对象以NSDefaultRunLoopMode（kCFRunLoopDefaultMode）添加到主运行循环以后，滑动scrollview的时候NSTimer却不动了？

## 34.苹果是如何实现Autorelease Pool的？

- autoreleasepool 以一个队列数组的形式实现,主要通过下列三个函数完成.
    * objc_autoreleasepoolPush
    * objc_autoreleasepoolPop
    * objc_autorelease
    
看函数名就可以知道，对 autorelease 分别执行 push，和 pop 操作。销毁对象时执行release操作。
- 举例说明：我们都知道用类方法创建的对象都是 Autorelease 的，那么一旦 Person 出了作用域，当在 Person 的 dealloc 方法中打上断点，我们就可以看到这样的调用堆栈信息

![image](https://camo.githubusercontent.com/1e77679169328e5128722b3268bf9a488fc00ae2/687474703a2f2f6936302e74696e797069632e636f6d2f31356d666a31312e6a7067)

## 35.isa指针？（对象的isa，类对象的isa，元类的isa都要说）

- sa指针是什么？
    * 我们经常使用id来声明一个对象，本质上，我们创建的一个对象或实例其实就是一个struct objc_object结构体，而我们常用的id也就是这个结构体的指针。这个结构体只有一个成员变量，这是一个Class类型的变量isa，也是一个结构体									指针。面向对象中每一个对象都必须依赖一个类来创建，因此对象的isa指针就指向对象所属的类根据这个类模板能够创建出实例变量、实例方法等。
- 对象的isa指针
    * 每个实例对象有个isa的指针,他指向对象的类
- 类对象的isa指针
    * Class里也有个isa的指针, 指向meteClass(元类)。
- 元类的isa指针
    * 元类保存了类方法的列表。当类方法被调用时，先会从本身查找类方法的实现，如果没有，元类会向他父类查找该方法。同时注意的是：元类（meteClass）也是类，它也是对象。元类也有isa指针,它的isa指针最终指向的是一个根元类(root meteClass).根元类的isa指针指向本身，这样形成了一个封闭的内循环。

![image](http://hi.csdn.net/attachment/201201/19/0_1326963670oeC1.gif)

参考文献：
- [《iOS class深入理解： 实例对象、类对象、元类和isa指针》](http://www.zhimengzhe.com/IOSkaifa/253119.html)
- [《iOS中isa指针》](https://blog.csdn.net/miao_em/article/details/56671616)

## 36.类方法和实例方法有什么区别？

- 类方法：
    * 类方法是属于类对象的
    * 类方法只能通过类对象调用
    * 类方法中的self是类对象
    * 类方法可以调用其他的类方法
    * 类方法中不能访问成员变量
    * 类方法中不能直接调用对象方法

- 实例方法：
    * 实例方法是属于实例对象的
    * 实例方法只能通过实例对象调用
    * 实例方法中的self是实例对象
    * 实例方法中可以访问成员变量
    * 实例方法中直接调用实例方法
    * 实例方法中也可以调用类方法(通过类名)

## 37.介绍一下分类，能用分类做什么？内部是如何实现的？它为什么会覆盖掉原来的方法？

## 38.运行时能增加成员变量么？能增加属性么？如果能，如何增加？如果不能，为什么？

## 39.objc中向一个nil对象发送消息将会发生什么？（返回值是对象，是标量，结构体）

## 40.UITableview的优化方法（缓存高度，异步绘制，减少层级，hide，避免离屏渲染

## 41.有没有用过运行时，用它都能做什么？（交换方法，创建类，给新创建的类增加方法，改变isa指针）

## 42.看过哪些第三方框架的源码？都是如何实现的？（如果没有，问一下多图下载的设计）

## 43.SDWebImage的缓存策略？

- 减少网络流量，下载完图片后存储到本地，下载再获取同一张图片时，直接从本地获取，提升用户体验，能快速从本地获取呈现给用户。
SDWebImage提供了对图片进行了缓存，主要由SDImageCache完成。该类负责处理内存缓存以及一个可选的磁盘缓存，其中磁盘缓存的写操作是异步的，不会对UI造成影响。
- 内存缓存及磁盘缓存
    * 内存缓存的处理由NSCache对象实现，NSCache类似一个集合的容器，它存储key-value对，类似于nsdictionary类，我们通常使用缓存来临时存储短时间使用但创建昂贵的对象，重用这些对象可以优化新能，同时这些对象对于程序来说不是紧要的，如果内存紧张就会自动释放。
    * 磁盘缓存的处理使用NSFileManager对象实现，图片存储的位置位于cache文件夹，另外SDImageCache还定义了一个串行队列来异步存储图片。
    * SDImageCache提供了大量方法来缓存、获取、移除及清空图片。对于图片的索引，我们通过一个key来索引，在内存中，我们将其作为NSCache的key值，而在磁盘中，我们用这个key值作为图片的文件名，对于一个远程下载的图片其url实作为这个key的最佳选择。
- 存储图片
    * 先在内存中放置一份缓存，如果需要缓存到磁盘，将磁盘缓存操作作为一个task放到串行队列中处理，会先检查图片格式是jpeg还是png，将其转换为响应的图片数据，最后把数据写入磁盘中（文件名是对key值做MD5后的串）。
- 查询图片
    * 内存和磁盘查询图片API：

```
- (UIImage *)imageFromMemoryCacheForKey:(NSString *)key;
- (UIImage *)imageFromDiskCacheForKey:(NSString *)key;
```
查看本地是否存在key指定的图片，使用一下API：

```

```


- SDWebImage加载图片的流程
    * 入口 setImageWithURL:placeholderImage:options:会先把 placeholderImage显示，然后 SDWebImageManager根据 URL 开始处理图片。
    * 进入SDWebImageManager类中downloadWithURL:delegate:options:userInfo:，交给
SDImageCache从缓存查找图片是否已经下载
queryDiskCacheForKey:delegate:userInfo:.
    * 先从内存图片缓存查找是否有图片，如果内存中已经有图片缓存，SDImageCacheDelegate回调 imageCache:didFindImage:forKey:userInfo:到
SDWebImageManager。
    * SDWebImageManagerDelegate 回调
webImageManager:didFinishWithImage: 到 UIImageView+WebCache,等前端展示图片。
    * 如果内存缓存中没有，生成 ｀NSOperation ｀
添加到队列，开始从硬盘查找图片是否已经缓存。
    * 根据 URL的MD5值Key在硬盘缓存目录下尝试读取图片文件。这一步是在 NSOperation 进行的操作，所以回主线程进行结果回调 notifyDelegate:。
    * 如果上一操作从硬盘读取到了图片，将图片添加到内存缓存中（如果空闲内存过小， 会先清空内存缓存）。SDImageCacheDelegate'回调 imageCache:didFindImage:forKey:userInfo:`。进而回调展示图片。
    * 如果从硬盘缓存目录读取不到图片，说明所有缓存都不存在该图片，需要下载图片， 回调 imageCache:didNotFindImageForKey:userInfo:。
    * 共享或重新生成一个下载器 SDWebImageDownloader开始下载图片。
    * 图片下载由 NSURLConnection来做，实现相关 delegate
来判断图片下载中、下载完成和下载失败。
    * connection:didReceiveData: 中利用 ImageIO做了按图片下载进度加载效果。
    * connectionDidFinishLoading: 数据下载完成后交给 SDWebImageDecoder做图片解码处理。   
    * 图片解码处理在一个 NSOperationQueue完成，不会拖慢主线程 UI.如果有需要 对下载的图片进行二次处理，最好也在这里完成，效率会好很多。
    * 在主线程 notifyDelegateOnMainThreadWithInfo:
宣告解码完成 imageDecoder:didFinishDecodingImage:userInfo: 回调给 SDWebImageDownloader`。
    * imageDownloader:didFinishWithImage:回调给 SDWebImageManager告知图片 下载完成。
    * 通知所有的 downloadDelegates下载完成，回调给需要的地方展示图片。
    * 将图片保存到 SDImageCache中，内存缓存和硬盘缓存同时保存。写文件到硬盘 也在以单独 NSOperation 完成，避免拖慢主线程。
    * SDImageCache 在初始化的时候会注册一些消息通知，
在内存警告或退到后台的时 候清理内存图片缓存，应用结束的时候清理过期图片。

## 44.AFN为什么添加一条常驻线程？

## 45.KVO的使用？实现原理？（为什么要创建子类来实现）

- KVO 是 Objective-C 对观察者设计模式的一种实现。
- KVO 提供一种机制，指定一个被观察对象(例如 A 类)，当对象某个属性(例如 A 中的字符串 name)发生更改时，对象会获得通知，并作出相应处理；
- KVO的使用
    * 最常见的KVO运用是监听scrollView的contentOffset属性，来完成用户滚动时动态改变某些控件的属性实现效果，包括渐变导航栏、下拉刷新控件等效果。
    * 
- KVO的实现方法（苹果 API 文档中的方法）
    * 注册观察者：
    
```
//第一个参数 observer：观察者 （这里观察self.myKVO对象的属性变化）
//第二个参数 keyPath： 被观察的属性名称(这里观察 self.myKVO 中 num 属性值的改变)
//第三个参数 options： 观察属性的新值、旧值等的一些配置（枚举值，可以根据需要设置，例如这里可以使用两项）
//第四个参数 context： 上下文，可以为 KVO 的回调方法传值（例如设定为一个放置数据的字典）
[self.myKVO addObserver:self forKeyPath:@"num" options:

```

-     
    * 属性(keyPath)的值发生变化时，收到通知，调用以下方法:
    
```
//keyPath:属性名称
//object:被观察的对象
//change:变化前后的值都存储在 change 字典中
//context:注册观察者时，context 传过来的值
-(void)observeValueForKeyPath:(NSString *)keyPath ofObject:(id)object change:(NSDictionary<NSString *,id> *)change context:(void *)context
{
}

```

- KVO 实现原理
    * KVO 在 Apple 中的 API 文档如下：
>    Automatic key-value observing is implemented using a technique called 
isa-swizzling… When an observer is registered for an attribute of an object the 
isa pointer of the observed object is modified, pointing to an intermediate class 
rather than at the true class …

- 
    * KVO 的实现依赖于 Objective-C 强大的 Runtime，从以上 Apple 的文档可以看出苹果对于 KVO 机制的实现是一笔带过，而具体的细节没有过多的描述。
    * 当观察某对象 A 时，KVO 机制动态创建一个对象A当前类的子类，并为这个新的子类重写了被观察属性 keyPath 的 setter 方法。setter 方法随后负责通知观察对象属性的改变状况。
    * Apple 使用了 isa 混写（isa-swizzling）来实现 KVO 。当观察对象A时，KVO机制动态创建一个新的名为：NSKVONotifying_A 的新类，该类继承自对象A的本类，且 KVO 为 NSKVONotifying_A 重写观察属性的 setter 方法，setter 方法会负责在调用原 setter 方法之前和之后，通知所有观察对象属性值的更改情况。
    * NSKVONotifying_A 类剖析：在这个过程，被观察对象的 isa 指针从指向原来的 A 类，被 KVO 机制修改为指向系统新创建的子类 NSKVONotifying_A 类，来实现当前类属性值改变的监听；
所以当我们从应用层面上看来，完全没有意识到有新的类出现，这是系统“隐瞒”了对 KVO 的底层实现过程，让我们误以为还是原来的类。但是此时如果我们创建一个新的名为“NSKVONotifying_A”的类，就会发现系统运行到注册 KVO 的那段代码时程序就崩溃，因为系统在注册监听的时候动态创建了名为 NSKVONotifying_A 的中间类，并指向这个中间类了。
（isa 指针的作用：每个对象都有 isa 指针，指向该对象的类，它告诉 Runtime 系统这个对象的类是什么。所以对象注册为观察者时，isa 指针指向新子类，那么这个被观察的对象就神奇地变成新子类的对象（或实例）了。） 因而在该对象上对 setter 的调用就会调用已重写的 setter，从而激活键值通知机制。
    * 子类setter方法剖析：KVO 的键值观察通知依赖于 NSObject 的两个方法:willChangeValueForKey:和 didChangevlueForKey:，在存取数值的前后分别调用 2 个方法：
被观察属性发生改变之前，willChangeValueForKey:被调用，通知系统该 keyPath 的属性值即将变更；当改变发生后， didChangeValueForKey: 被调用，通知系统该 keyPath 的属性值已经变更；之后， observeValueForKey:ofObject:change:context: 也会被调用。且重写观察属性的 setter 方法这种继承方式的注入是在运行时而不是编译时实现的。

KVO 为子类的观察者属性重写调用存取方法的工作原理在代码中相当于：

```
-(void)setName:(NSString *)newName{ 
[self willChangeValueForKey:@"name"];    //KVO 在调用存取方法之前总调用 
[super setValue:newName forKey:@"name"]; //调用父类的存取方法 
[self didChangeValueForKey:@"name"];     //KVO 在调用存取方法之后总调用
}

```
- 为什么要创建子类来实现
    * 触发通知方式：
        * 自动通知：这种应该是比较常见的，原因在于NSObject类实现了NSKeyValueCoding协议，因此只要是继承了NSObject类的对象通过KVC进行操作就可以自动的通知到观察者。
        * 手动通知：这就需要让你的类重写+ (BOOL)automaticallyNotifiesObserversForKey:(NSString *)key或者是+ (BOOL)automaticallyNotifiesObserversOf<key>方法，对于想要手动触发通知的，可以根据keyPath返回NO，而其对于其他位置的keyPath，要返回父类的这个方法。
            * 要实现手动通知，你需要在值改变前调用 willChangeValueForKey: 方法，在值改变后调用 didChangeValueForKey: 方法。你可以在发送通知前检查值是否改变，如果没有改变就不发送通知。关键在于willChangeValueForKey:以及didChangeValueForKey:这两个方法，自动通知应该就是在子类重写的setter中封装好触发通知的逻辑。
            * 其实手动触发通知有一个细节的地方，不知道有没有人注意到，就是当你设置某个键值需要手动通知时，系统并没有去动态创建带前缀NSKVONotifying_原类名，你可以通过rumtime的object_getClass(self)，去验证self的isa是否指向新类，答案是没有。
    * 触发键值观察的关键方法willChangeValueForKey:和didChangeValueForKey:，我们做个假设，假设苹果KVO机制并没有通过创建子类实现，而是在当前类实现。那么会存在一个问题，就是开发者重写该属性的setter方法，并且并没有去执行willChangeValueForKey:和didChangeValueForKey:两个方法，就不会触发通知观察者。
    * 有可能跟类设计的单一责任原则有关，子类自负责封装触发通知逻辑，其他的一概不管（例如获取旧值以及赋值新值都会执行父类的方法）。

## 46.KVC的使用？实现原理？（KVC拿到key以后，是如何赋值的？知不知道集合操作符，能不能访问私有属性，能不能直接访问_ivar）

## 47.有已经上线的项目么？

## 48.项目里哪个部分是你完成的？（找一个亮点问一下如何实现的）

## 49.开发过程中遇到过什么困难，是如何解决的？

## 50.遇到一个问题完全不能理解的时候，是如何帮助自己理解的？举个例子？

## 51.有看书的习惯么？最近看的一本是什么书？有什么心得？

## 52.有没有使用一些笔记软件？会在多平台同步以及多渠道采集么？（如果没有，问一下是如何复习知识的）

## 53.有没有使用清单类，日历类的软件？（如果没有，问一下是如何安排，计划任务的）

## 54.平常看博客么？有没有自己写过？（如果写，有哪些收获？如果没有写，问一下不写的原因）