# iOSInterviewQuestion
## 微博@Liberalisman面试知识点总结（附答案）

- 03《微博@Liberalisman面试知识点总结》，面试题来源是微博[@Liberalisman](https://weibo.com/1743643682/)的面试题知识点总结；
- 如有纰漏，请向微博[@爱吃兔兔的胡萝卜吖](https://weibo.com/6447187962/)反馈。

### 推荐书目
* 1.《Effective Objective-C 2.0》
* 2.《Objective-C 高级编程》
* 3.《程序员的自我修养》
* 4.《图解HTTP》
* 5.《高性能iOS应用开发》
* 6.《算法图解》
* 7.《剑指Offer》

# 索引
## 0.数据结构及算法


### ①.数据结构
- 1.数组
- 2.字符串
- 3.链表
- 4.树
- 5.栈
- 6.队列
- 7.哈希表（有哪些功能是通过哈希表实现的）

### ②.算法


[推荐一个很好的算法总结](https://github.com/CyC2018/Interview-Notebook)

- 1.字符串反转 - [链接](https://github.com/liberalisman/iOS-InterviewQuestion-collection/blob/master/0.算法集合/1.第一题.md)
- 2.链表反转
- 3.有序数组合并
- 4.Hash 算法
- 5.查找两个子视图的共同父视图
- 6.无序数组中的中位数
- 7.两数之和为特定值

## 1.iOS 内存管理
- 1.[讲一下 `iOS` 内存管理的理解？(三种方案的结合)](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博@Liberalisman面试知识点总结》/03《微博@Liberalisman面试知识点总结》.md#1讲一下-ios-内存管理的理解三种方案的结合) 
- 2.使用自动引用计（`ARC`）数应该遵循的原则? 
- 3.`ARC` 自动内存管理的原则？ 
- 4.访问 `__weak` 修饰的变量，是否已经被注册在了 `@autoreleasePool` 中？为什么？ 
- 5.`ARC` 的 `retainCount` 怎么存储的？ 
- 6.简要说一下 `@autoreleasePool` 的数据结构？ 
- 7.`__weak` 和 `_Unsafe_Unretain` 的区别？ 
- 8.为什么已经有了 `ARC` ,但还是需要 `@AutoreleasePool` 的存在？ 
- 9.`__weak` 属性修饰的变量，如何实现在变量没有强引用后自动置为 `nil`？ 
- 10.说一下对 `retain`,`copy`,`assign`,`weak`,`_Unsafe_Unretain` 关键字的理解。 
- 11.`ARC` 在编译时做了哪些工作？ 
- 12.`ARC` 在运行时做了哪些工作？ 
- 13.函数返回一个对象时，会对对象 `autorelease` 么？为什么？ 
- 14.说一下什么是 `悬垂指针`？什么是 `野指针`? 
- 15.内存管理默认的关键字是什么？ 
- 16.内存中的5大区分别是什么？ 
- 17.是否了解 `深拷贝` 和 `浅拷贝` 的概念，集合类深拷贝如何实现？ 
- 18.`BAD_ACCESS` 在什么情况下出现? 
- 19.讲一下 `@dynamic` 关键字？
- 20.`@autoreleasrPool` 的释放时机？
- 21.`retain`、`release` 的实现机制？
- 22.能不能简述一下 `Dealloc` 的实现机制？


## 2.Runtime
- 1.实例对象的数据结构？
- 2.类对象的数据结构？
- 3.元类对象的数据结构? 
- 4.`Category` 的实现原理？ 
- 5.如何给 `Category` 添加属性？关联对象以什么形式进行存储？ 
- 6.`Category` 有哪些用途？ 
- 7.`Category` 和 `Extension` 有什么区别？
- 8.说一下 `Method Swizzling`? 说一下在实际开发中你在什么场景下使用过? 
- 9.如何实现动态添加方法和属性？ 
- 10.说一下对 `isa` 指针的理解， 对象的`isa` 指针指向哪里？`isa` 指针有哪两种类型？（注意区分不同对象） 
- 11.`Obj-C` 中的类信息存放在哪里？ 
- 12.一个 `NSObject` 对象占用多少内存空间？
- 13.说一下对 `class_rw_t` 的理解？
- 14.说一下对 `class_ro_t` 的理解？
- 15.说一下 `Runtime` 消息解析。
- 16.说一下 `Runtime` 消息转发。
- 17.如何运用 `Runtime` 字典转模型？
- 18.如何运用 `Runtime` 进行模型的归解档？
- 19.在 `Obj-C` 中为什么叫发消息而不叫函数调用？
- 20.说一下对 `runtime` 的理解。（主要讲一下消息机制，是对上述的总结）
- 21.说一下 `Runtime` 的方法缓存？存储的形式、数据结构以及查找的过程？
- 22.是否了解 `Type Encoding`? 


## 3.Runloop
- 1.`Runloop` 和线程的关系？ 
- 2.讲一下 `Runloop` 的 `Mode`?(越详细越好) 
- 3.讲一下 `Observer` ？（Mode中的重点） 
- 4.讲一下 `Runloop` 的内部实现逻辑？（运行过程） 
- 5.你所知的哪些三方框架使用了 `Runloop`?（AFNetworking、Texture 等）
- 6.`autoreleasePool` 在何时被释放？ 
- 7.解释一下 `事件响应` 的过程？ 
- 8.解释一下 `手势识别` 的过程？ 
- 9.解释一下 `GCD` 在 `Runloop` 中的使用？ 
- 10.解释一下 `NSTimer`，以及 `NSTimer` 的循环引用。 
- 11.`AFNetworking` 中如何运用 `Runloop`? 
- 12.`PerformSelector` 的实现原理？
- 13.利用 `runloop` 解释一下页面的渲染的过程？
- 14.如何使用 `Runloop` 实现一个常驻线程？这种线程一般有什么作用？
- 15.为什么 `NSTimer` 有时候不好使？（不同类型的Mode）
- 16.`PerformSelector:afterDelay:`这个方法在子线程中是否起作用？为什么？怎么解决？
- 17.什么是异步绘制？


## 4.网络
- 1.`NSUrlConnect`相关知识。
- 2.`NSUrlSession`相关知识。
- 3.`Http` 和 `Https` 的区别？为什么更加安全？
- 4.`Http`的请求方式有哪些？`Http` 有什么特性？
- 5.解释一下 `三次握手` 和 `四次挥手`？解释一下为什么是`三次握手` 又为什么是 `四次挥手`？
- 6.`GET` 和 `POST` 请求的区别？
- 7.`HTTP` 请求报文 和 响应报文的结构？
- 8.什么是 `Mimetype` ? 
- 9.数据传输的加密过程？ 
- 10.说一下 `TCP/IP` 五层模型的协议? 
- 11.说一下 `OSI` 七层模型的协议? 
- 12.`大文件下载` 的功能有什么注意点？ 
- 13.`断点续传` 功能该怎么实现？ 
- 14.封装一个网络框架有哪些注意点？
- 15.`Wireshark`、`Charles`、`Paw` 等工具会使用吗？
- 16.`NSUrlProtocol`用过吗？用在什么地方了？
- 17.如何在测试过程中 `MOCK` 各种网络环境？ 
- 18.`DNS` 的解析过程？网络的 `DNS` 优化。 
- 19.`Post`请求体有哪些格式？ 
- 20.网络请求的状态码都大致代表什么意思？
- 21.抓包软件 `Charles` 的原理是什么？说一下中间人攻击的过程。
- 22.如何判断一个请求是否结束？
- 23.`SSL` 传输协议？说一下 `SSL` 验证过程？
- 24.解释一下 `Http` 的持久连接？
- 25.说一下传输控制协议 - `TCP` ?
- 26.说一下用户数据报协议 - `UDP` ? 
- 27.谈一谈网络中的 `session` 和 `cookie`? 

## 5.多线程
- 1.`NSThread`相关知识？ 
- 2.`GCD` 相关知识？ 
- 3.`NSOperation` 和 `NSOperationQueue`相关知识？ 
- 4.如何实现线性编程？ 
- 5.说一下 `GCD` 并发队列实现机制？
- 6.`NSLock` 
- 7.`NSContion`
- 8.条件锁 - `NSContionLock`
- 9.递归锁 - `NSRecursiveLock`
- 10.同步锁 - `Synchronized(self) {// code}`
- 11.信号量 - `dispatch_semaphore`。 
- 12.自旋锁 - `OSSpinLock` 。 
- 13.互斥锁 - `pthread_mutex`
- 14.分步锁 - `NSDistributedLock`。
- 15.如何确保线程安全？ 
- 16.`NSMutableArray`、和 `NSMutableDictionary`是线程安全的吗？`NSCache`呢？ 

## 6.项目架构
- 1.什么是 `MVC`?
- 2.什么是 `MVVM`?
- 3.什么是 `MVP`?
- 4.什么是 `CDD`?
- 5.项目的组件化？
    - 1.说一下你了解的项目组件化方案？
    - 2.什么样的团队及项目适合采用组件化的形式进行开发？
    - 3.组件之间的通信方式。
    - 4.各组件之间的解耦。
- 6.还了解哪些项目架构？你之前所在公司的架构师什么样的，简单说一下？

## 7.消息传递的方式

- 1.说一下 `NSNotification` 的实现机制？
- 2.说一下 `NSNotification` 的特点。
- 3.简述 `KVO` 的实现机制。
- 4.`KVO` 在使用过程中有哪些注意点？有没有使用过其他优秀的 `KVO` 三方替代框架？ 
- 5.简述 `KVO` 的注册依赖键是什么？
- 6.如何做到 `KVO` 手动通知？
- 7.在什么情况下会触发 `KVO`?
- 8.给实例变量赋值时，是否会触发 `KVO`?
- 9.`Delegate`通常用什么关键字修饰？为什么？
- 10`通知` 和 `代理` 有什么区别？各自适应的场景？
- 11.`__block` 的解释以及在 `ARC` 和 `MRC` 下有什么不同？
- 12.`Block` 的内存管理。
- 13.`Block` 自动截取变量。
- 14.`Block` 处理循环引用。
- 15.`Block` 有几种类型？分别是什么？

## 8.数据存储
- 1.Sqlite3 （不同版本的APP，数据库结构变化了，如何处理? ）
- 2.FMDB (`Sqlite3` 的封装)
- 3.Realm
- 4.NSKeyArchieve
- 5.Preperfence
- 6.Plist
- 7.CoreDate
- 8.Keychain
- 9.UIPasteBoard(感谢 lilingyu0620 同学提醒)
- 10.FoundationDB

## 9.iOS设计模式

> 这个模块需要大量代码，我就不贴了

- 1.编程中的六大设计原则？ - [链接](https://github.com/liberalisman/iOS-InterviewQuestion-collection/blob/master/9.设计模式/1.第一题.md)
- 2.如何设计一个图片缓存框架？ - [链接](https://github.com/liberalisman/iOS-InterviewQuestion-collection/blob/master/9.设计模式/2.第二题.md)
- 3.如何设计一个时长统计框架？ - [链接](https://github.com/liberalisman/iOS-InterviewQuestion-collection/blob/master/9.设计模式/3.第三题.md)
- 4.类工厂模式
- 5.外观模式
- 6.中介者模式
- 7.访问者模式
- 8.装饰模式 
- 9.观察者模式
- 10.责任链模式
- 11.命令模式
- 12.适配器模式
- 13.桥接模式
- 14.代理委托模式
- 15.单例模式


## 10.音频处理

## 11.视频处理

## 12.图像处理
- 1.图像的压缩、解压。

## 13.iOS 动画

## 14.蓝牙

## 15.ARKit

## 16.Core ML

## 17.代码管理、持续集成、项目托管
- 1.Git
    - 1.`git pull` 和 `git fetch` 的区别？
    - 2.`git merge` 和 `git rebase` 的区别？ 
- 2.Svn
- 3.CocoaPods
    - 1.说一下 `CocoaPods` 的原理？
    - 2.如何让自己写的框架支持 `CocoaPods`？
    - 3.`pod update` 和 `pod install` 有什么区别？
    - 4.`Podfile.lock` 文件起什么作用？
    - 5.如何集成本地私有库？
    - 6.如何集成远程私有库 ？
- 4.Carthage
- 5.Fastlane
- 6.Jenkins
- 7.fir.im
- 8.蒲公英
- 9.TestFlight

## 18.数据安全及加密
- 1.RSA非对称加密  
- 2.AES对称加密
- 3.DES加密
- 4.Base64加密
- 5.MD5加密
- 6.简述 `SSL` 加密的过程用了哪些加密方法，为何这么作？
- 7.是否了解 `iOS` 的签名机制？
- 8.如何对 `APP` 进行重签名？

## 19.源代码阅读
- 1.YYKit
- 2.SDWebImage
- 3.AFNetworking
- 4.SVProgressHub 
- 5.Texture（ASDK）

## 20.iOS逆向及安全

## 21.性能优化
- 1.如何提升 `tableview` 的流畅度？
- 2.如何使用 `Instruments` 进行性能调优？(Time Profiler、Zombies、Allocations、Leaks)
- 3.如何优化 `APP` 的启动时间？（感谢 @静待海棠花开 的提醒）
- 4.如何对 `APP` 进行内存、电量、网络流量的优化？（感谢 @静待海棠花开 的提醒）
- 5.如何有效降低 `APP` 包的大小？
- 6.日常如何检查内存泄露？
- 7.能不能说一下物理屏幕显示的原理？
- 8.解释一下什么是屏幕卡顿、掉帧？该如何避免？
- 9.什么是 `离屏渲染`？什么情况下会触发？该如何应对？

## 22.调试技巧 & 软件使用
- 1.`LLDB` 调试。
- 2.断点调试。
- 3.`NSAssert` 的使用。
- 4.`Charles` 的使用。
- 5.`Reveal` 的使用。

## 23.扩展问题
- 1.无痕埋点
- 2.APM（应用程序性能监测）
- 3.Hot Patch（热修补）
- 4.崩溃的处理

## 24.其他问题
- 1.`UIView` 和 `CALayer` 是什么关系？
- 2.`Bounds` 和 `Frame` 的区别?
- 3.`nil`、`NIL`、`NSNULL` 有什么区别？
- 4.如何实现一个线程安全的 `NSMutableArray`?
- 5.如何定义一台 `iOS` 设备的唯一性?
- 6.如何高性能的画一个圆角？
- 7.`load` 和 `Initialize` 的区别?
- 8.`Designated Initializer`的规则？
- 9.`App` 编译过程有了解吗？
- 10.`JS` 和 `Native` 交互。
- 11.使用 `atomic` 一定是线程安全的吗？
- 12.`LoadView`方法了解吗？
- 13.说一下对 `APNS` 的认识？
- 14.实现 `isEqual` 和 `hash` 方法时要注意什么？
- 15.`UIButton` 的父类是什么？`UILabel` 的父类又是什么？
- 16.实现一个控件，可以浮在任意界面的上层并支持拖动？
- 17.解释一下 `copy` 关键字涉及的方方面面，说的越全越好。
- 18.说一下控制器 `View` 的生命周期，一旦收到内存警告会如何处理？
- 19.简述事件传递、事件响应机制。
- 20.说一下对 `Super` 关键字的理解。
- 21.了解 `逆变` 和 `协变` 吗？
- 22.`@synthesize` 和 `@dynamic` 分别有什么作用？
- 23.`Obj-C` 中的反射机制了解吗？
- 24.`atomic` 修饰的属性是绝对安全的吗？为什么？
- 25.`id` 和 `instanceType` 有什么区别？



## 25.计算题
1.**输出如下的计算结果**

```objc
int a=5,b;
b=(++a)+(++a);
```

## 26.开放性问题

- 1.你最近在业余时间研究那些技术点？可不可以分享一下你的心得？
- 2.你对自己未来的职业发展有什么想法？有没有对自己做过职业规划？
- 3.和同事产生矛盾（包括意见分歧），你一般怎么解决？
- 4.能不能说一下你的业余精力都花在什么方面，或者介绍一下你的爱好？
- 5.学习技术知识通常通过哪些途径？
- 6.遇到疑难问题一般怎么解决？能不能说一个你印象颇深的技术难点，后来怎么解决的？


# 0.数据结构及算法


## ①.数据结构
### 1.数组
### 2.字符串
### 3.链表
### 4.树
### 5.栈
### 6.队列
### 7.哈希表（有哪些功能是通过哈希表实现的）

## ②.算法


[推荐一个很好的算法总结](https://github.com/CyC2018/Interview-Notebook)

### 1.字符串反转 
### 2.链表反转
### 3.有序数组合并
### 4.Hash 算法
### 5.查找两个子视图的共同父视图
### 6.无序数组中的中位数
### 7.两数之和为特定值

## 1. iOS 内存管理

### 1.讲一下 `iOS` 内存管理的理解？(三种方案的结合)  

OC中的内存管理主要有三种方式：ARC、MRC、自动释放池
* MRC（MannulReference Counting）手动引用计数
* ARC（automatic reference counting）自动引用计数
* 在5.0版本以前，OC内存管理遵循“谁创建、谁释放、谁引用、谁管理”的机制，当创建或引用一个对象的时候，需要向她发送alloc、copy、retain消息，当释放该对象时需要发送release消息，当对象引用计数为0时，系统将释放该对象，其实这也是手动管理机制。
* 在5.0以后，引用自动管理机制，其实管理机制和手动管理机制一样，只是不再需要调用retain、release、autorelease；它编译时的特性，当你使用ARC时，在适当位置插入release和autorelease；它引用strong和weak关键字，strong修饰的指针变量指向对象时，当指针指向新值或者指针不复存在，相关联的对象就会自动释放，而weak修饰的指针变量指向对象，当对象的拥有者指向新值或者不存在时weak修饰的指针会自动置为nil。如果使用alloc、copy或者retain一个对象时，你就有义务，向它发送一条release或者autorelease消息。其他方法创建的对象，不需要由自己来管理内存
* 自动释放池：（NSAutoRealeasePool）可以通过创建和释放内存池控制内存申请和收回的时机。向一个对象发送一条autorelease消息，这个对象并不会立即销毁，而是将这个对象放入了自动释放池，待池子释放时，它会向池子中每一个对象发送一条release详细，以此来释放对象。向一个对象发送release消息，并不意味着这个对象被销毁了，而是当这个对象的引用计数为0时，系统才会调用dealloc方法，释放该对象和对象本身他所拥有的实例。

也就是说，iOS中对内存管理的机制（堆内存），是通过 retainCount 的机制来决定对象是否需要释放。每一个对象都有一个与之关联的retainCount， 每次runloop迭代结束后，都会检查对象的 retainCount，如果retainCount等于0，就说明该对象没有地方需要继续使用它，可以被释放掉了。无论是手动管理内存，还是ARC机制，都是通过对retainCount来进行内存管理的。

#### 引用计数如何储存（三种方案的结合）

* 第一种方案：TaggedPointer
    - 一个普通的iOS程序，如果没有Tagged Pointer对象，从32位机器迁移到64位机器中后，虽然逻辑没有任何变化，但像NSNumber、NSDate一类的对象所占用的内存会翻倍，进而浪费内存。为了存储和访问一个NSNumber对象，我们需要在堆上为其分配内存，另外还要维护它的引用计数，管理它的生命期。这些都给程序增加了额外的逻辑，造成运行效率上的损失。为了改进上面提到的内存占用和效率问题，苹果提出了Tagged Pointer对象。
    - 我们将一个对象的指针拆成两部分，一部分直接保存数据，另一部分作为特殊标记，表示这是一个特别的指针，不指向任何一个地址。
    - Tagged Pointer特点
        - Tagged Pointer专门用来存储小的对象，例如NSNumber和NSDate
        - Tagged Pointer指针的值不再是地址了，而是真正的值。所以，实际上它不再是一个对象了，它只是一个披着对象皮的普通变量而已。所以，它的内存并不存储在堆中，也不需要malloc和free。
        - 在内存读取上有着3倍的效率，创建时比以前快106倍。
    - 总体来说，如果一个对象使用了Tagged Pointer技术（比如NSString，NSNumber等），指针里面会直接存数据内容，不会再作为“指针”指向其它地址，从Runtime来理解就是不会使用isa指针，也就不会继承苹果的内存管理方式（Reference Counting）。
    - 注意：所有对象都有 isa 指针，而Tagged Pointer其实是没有的，因为它不是真正的对象。 因为不是真正的对象，所以如果你直接访问Tagged Pointer的isa成员的话，在编译时将会有如下警告：
    ![image](https://res.infoq.com/articles/deep-understanding-of-tagged-pointer/zh/resources/0519063.jpg)
   
应该换成相应的方法调用，如 isKindOfClass 和 object_getClass。只要避免在代码中直接访问对象的isa变量，即可避免这个问题。
    
* 第二种方案：isa 指针（NONPOINTER_ISA）
    - 指针的内存空间很大，有时候可以优化指针，在指针中存储一部分内容。
    - 不同架构下的64位环境中isa指针结构:
    
```
union isa_t 
{
    isa_t() { }
    isa_t(uintptr_t value) : bits(value) { }

    Class cls;
    uintptr_t bits;

#if SUPPORT_NONPOINTER_ISA
# if __arm64__
#   define ISA_MASK        0x00000001fffffff8ULL
#   define ISA_MAGIC_MASK  0x000003fe00000001ULL
#   define ISA_MAGIC_VALUE 0x000001a400000001ULL
    struct {
        uintptr_t indexed           : 1;
        uintptr_t has_assoc         : 1;
        uintptr_t has_cxx_dtor      : 1;
        uintptr_t shiftcls          : 30; // MACH_VM_MAX_ADDRESS 0x1a0000000
        uintptr_t magic             : 9;
        uintptr_t weakly_referenced : 1;
        uintptr_t deallocating      : 1;
        uintptr_t has_sidetable_rc  : 1;
        uintptr_t extra_rc          : 19;
#       define RC_ONE   (1ULL<<45)
#       define RC_HALF  (1ULL<<18)
    };

# elif __x86_64__
#   define ISA_MASK        0x00007ffffffffff8ULL
#   define ISA_MAGIC_MASK  0x0000000000000001ULL
#   define ISA_MAGIC_VALUE 0x0000000000000001ULL
    struct {
        uintptr_t indexed           : 1;
        uintptr_t has_assoc         : 1;
        uintptr_t has_cxx_dtor      : 1;
        uintptr_t shiftcls          : 44; // MACH_VM_MAX_ADDRESS 0x7fffffe00000
        uintptr_t weakly_referenced : 1;
        uintptr_t deallocating      : 1;
        uintptr_t has_sidetable_rc  : 1;
        uintptr_t extra_rc          : 14;
#       define RC_ONE   (1ULL<<50)
#       define RC_HALF  (1ULL<<13)
    };

# else
    // Available bits in isa field are architecture-specific.
#   error unknown architecture
# endif

// SUPPORT_NONPOINTER_ISA
#endif

};

```

   - 只有arm64架构的设备支持优化，下面列出了isa指针中变量对应的含义:
 
变量名 | 含义
---|---
indexed | 0 表示普通的isa指针，1 表示使用优化，存储引用计数
has_assoc | 表示该对象是否包含 associated object，如果没有，则析构时会更快
has_cxx_dtor | 表示该对象是否有 C++ 或 ARC 的析构函数，如果没有，则析构时更快
shiftcls | 类的指针
magic | 固定值为 0xd2，用于在调试时分辨对象是否未完成初始化
weakly_referenced | 表示该对象是否有过weak对象，如果没有，则析构时更快
deallocating | 表示该对象是否正在析构
has_sidetable_rc | 表示该对象的引用计数值是否过大无法存储在isa指针
extra_rc | 存储引用计数值减一后的结果 

* 第三种方案：散列表
    - 散列表（Hash table，也叫哈希表），是根据关键码值(Key value)而直接进行访问的数据结构。也就是说，它通过把关键码值映射到表中一个位置来访问记录，以加快查找的速度。这个映射函数叫做散列函数，存放记录的数组叫做散列表。
    - 散列表就是把Key通过一个固定的算法函数既所谓的散列函数转换成一个整型数字即散列值，然后就将该数字对数组长度进行取余，取余结果就当作数组的下标，将value存储在以该数字为下标的数组空间里。而当使用散列表进行查询的时候，就是再次使用散列函数将key转换为对应的数组下标，并定位到该空间获取value，如此一来，就可以充分利用到数组的定位性能进行数据定位。
    - 哈希表的本质是一个数组，数组中每一个元素称为一个箱子(bin)，箱子中存放的是键值对。
    - 散列表来存储引用计数具体是用DenseMap类来实现，实现中有锁保证其安全性。
    - DenseMap类中包含好多映射实例到其引用计数的键值对，并支持用 DenseMapIterator 迭代器快速查找遍历这些键值对。
    - 引用计数表、weak表都是散列表；

### 2.使用自动引用计（`ARC`）数应该遵循的原则? 

ARC规则：
    - 不能使用retain/release/retainCount/autorelease
    - 不能使用NSAllocateObject/NSDeallocateObject
    - 必须遵守内存管理的方法命名规则
    - 不要显式调用dealloc
    - 使用@autoreleasepool块替代NSAutoreleasePool
    - 不能使用区域NSZone
    - 对象型变量不能作为c语言结构体的成员
    - 显式转换id和void*

### 3.`ARC` 自动内存管理的原则？ 

* 自己生成的对象，自己持有
* 非自己生成的对象，自己可以持有
* 自己持有的对象不再需要时，需要对其进行释放
* 非自己持有的对象无法释放

### 4.访问 `__weak` 修饰的变量，是否已经被注册在了 `@autoreleasePool` 中？为什么？

* 在访问__weak修饰的变量时，必定要访问注册到autoreleasepool的对象，这是因为：__weak修饰符只持有对象的弱引用，他不能持有对象实例，所以在超出其变量作用域时，对象即被释放。 而在访问引用对象的过程中，该对象可能被废弃，而如果把要访问的对象注册到autoreleasepool中，在@autoreleasepool块结束之前都能确保该对象存在。

### 5.`ARC` 的 `retainCount` 怎么存储的？ 
### 6.简要说一下 `@autoreleasePool` 的数据结构？ 
### 7.`__weak` 和 `_Unsafe_Unretain` 的区别？ 
### 8.为什么已经有了 `ARC` ,但还是需要 `@AutoreleasePool` 的存在？ 
### 9.`__weak` 属性修饰的变量，如何实现在变量没有强引用后自动置为 `nil`？ 
### 10.说一下对 `retain`,`copy`,`assign`,`weak`,`_Unsafe_Unretain` 关键字的理解。 
### 11.`ARC` 在编译时做了哪些工作？ 
### 12.`ARC` 在运行时做了哪些工作？ 
### 13.函数返回一个对象时，会对对象 `autorelease` 么？为什么？ 
### 14.说一下什么是 `悬垂指针`？什么是 `野指针`? 
### 15.内存管理默认的关键字是什么？ 
### 16.内存中的5大区分别是什么？ 
### 17.是否了解 `深拷贝` 和 `浅拷贝` 的概念，集合类深拷贝如何实现？ 
### 18.`BAD_ACCESS` 在什么情况下出现? 
### 19.讲一下 `@dynamic` 关键字？
### 20.`@autoreleasrPool` 的释放时机？
### 21.`retain`、`release` 的实现机制？
### 22.能不能简述一下 `Dealloc` 的实现机制？


## 2.Runtime
### 1.实例对象的数据结构？
### 2.类对象的数据结构？
### 3.元类对象的数据结构? 
### 4.`Category` 的实现原理？ 
### 5.如何给 `Category` 添加属性？关联对象以什么形式进行存储？ 
### 6.`Category` 有哪些用途？ 
### 7.`Category` 和 `Extension` 有什么区别？
### 8.说一下 `Method Swizzling`? 说一下在实际开发中你在什么场景下使用过? 
### 9.如何实现动态添加方法和属性？ 
### 10.说一下对 `isa` 指针的理解， 对象的`isa` 指针指向哪里？`isa` 指针有哪两种类型？（注意区分不同对象） 
### 11.`Obj-C` 中的类信息存放在哪里？ 
### 12.一个 `NSObject` 对象占用多少内存空间？
### 13.说一下对 `class_rw_t` 的理解？
### 14.说一下对 `class_ro_t` 的理解？
### 15.说一下 `Runtime` 消息解析。
### 16.说一下 `Runtime` 消息转发。
### 17.如何运用 `Runtime` 字典转模型？
### 18.如何运用 `Runtime` 进行模型的归解档？
### 19.在 `Obj-C` 中为什么叫发消息而不叫函数调用？
### 20.说一下对 `runtime` 的理解。（主要讲一下消息机制，是对上述的总结）
### 21.说一下 `Runtime` 的方法缓存？存储的形式、数据结构以及查找的过程？
### 22.是否了解 `Type Encoding`? 


## 3.Runloop
### 1.`Runloop` 和线程的关系？ 
### 2.讲一下 `Runloop` 的 `Mode`?(越详细越好)  
### 3.讲一下 `Observer` ？（Mode中的重点） 
### 4.讲一下 `Runloop` 的内部实现逻辑？（运行过程） 
### 5.你所知的哪些三方框架使用了 `Runloop`?（AFNetworking、Texture 等）
### 6.`autoreleasePool` 在何时被释放？ 
### 7.解释一下 `事件响应` 的过程？ 
### 8.解释一下 `手势识别` 的过程？ 
### 9.解释一下 `GCD` 在 `Runloop` 中的使用？ 
### 10.解释一下 `NSTimer`，以及 `NSTimer` 的循环引用。 
### 11.`AFNetworking` 中如何运用 `Runloop`? 
### 12.`PerformSelector` 的实现原理？
### 13.利用 `runloop` 解释一下页面的渲染的过程？
### 14.如何使用 `Runloop` 实现一个常驻线程？这种线程一般有什么作用？
### 15.为什么 `NSTimer` 有时候不好使？（不同类型的Mode）
### 16.`PerformSelector:afterDelay:`这个方法在子线程中是否起作用？为什么？怎么解决？
### 17.什么是异步绘制？


## 4.网络
### 1.`NSUrlConnect`相关知识。
### 2.`NSUrlSession`相关知识。
### 3.`Http` 和 `Https` 的区别？为什么更加安全？
### 4.`Http`的请求方式有哪些？`Http` 有什么特性？
### 5.解释一下 `三次握手` 和 `四次挥手`？解释一下为什么是`三次握手` 又为什么是 `四次挥手`？
### 6.`GET` 和 `POST` 请求的区别？
### 7.`HTTP` 请求报文 和 响应报文的结构？
### 8.什么是 `Mimetype` ? 
### 9.数据传输的加密过程？ 
### 10.说一下 `TCP/IP` 五层模型的协议? 
### 11.说一下 `OSI` 七层模型的协议? 
### 12.`大文件下载` 的功能有什么注意点？ 
### 13.`断点续传` 功能该怎么实现？ 
### 14.封装一个网络框架有哪些注意点？
### 15.`Wireshark`、`Charles`、`Paw` 等工具会使用吗？
### 16.`NSUrlProtocol`用过吗？用在什么地方了？ 
### 17.如何在测试过程中 `MOCK` 各种网络环境？ 
### 18.`DNS` 的解析过程？网络的 `DNS` 优化。 
### 19.`Post`请求体有哪些格式？ 
20.网络请求的状态码都大致代表什么意思？
### 21.抓包软件 `Charles` 的原理是什么？说一下中间人攻击的过程。
### 22.如何判断一个请求是否结束？
### 23.`SSL` 传输协议？说一下 `SSL` 验证过程？
### 24.解释一下 `Http` 的持久连接？
### 25.说一下传输控制协议 - `TCP` ?
### 26.说一下用户数据报协议 - `UDP` ? 
### 27.谈一谈网络中的 `session` 和 `cookie`? 

## 5.多线程
### 1.`NSThread`相关知识？ 
### 2.`GCD` 相关知识？ 
### 3.`NSOperation` 和 `NSOperationQueue`相关知识？ 
### 4.如何实现线性编程？ 
### 5.说一下 `GCD` 并发队列实现机制？
### 6.`NSLock` 
### 7.`NSContion`
### 8.条件锁 - `NSContionLock`
### 9.递归锁 - `NSRecursiveLock`
### 10.同步锁 - `Synchronized(self) {// code}`
### 11.信号量 - `dispatch_semaphore`。 
### 12.自旋锁 - `OSSpinLock` 。 
### 13.互斥锁 - `pthread_mutex`
### 14.分步锁 - `NSDistributedLock`。
### 15.如何确保线程安全？ 
### 16.`NSMutableArray`、和 `NSMutableDictionary`是线程安全的吗？`NSCache`呢？ 

## 6.项目架构
### 1.什么是 `MVC`?
### 2.什么是 `MVVM`?
### 3.什么是 `MVP`?
### 4.什么是 `CDD`?
### 5.项目的组件化？
* 1.说一下你了解的项目组件化方案？
* 2.什么样的团队及项目适合采用组件化的形式进行开发？
* 3.组件之间的通信方式。
* 4.各组件之间的解耦。

### 6.还了解哪些项目架构？你之前所在公司的架构师什么样的，简单说一下？

## 7.消息传递的方式

### 1.说一下 `NSNotification` 的实现机制？
### 2.说一下 `NSNotification` 的特点。
### 3.简述 `KVO` 的实现机制。
### 4.`KVO` 在使用过程中有哪些注意点？有没有使用过其他优秀的 `KVO` 三方替代框架？ 
### 5.简述 `KVO` 的注册依赖键是什么？
### 6.如何做到 `KVO` 手动通知？
### 7.在什么情况下会触发 `KVO`?
### 8.给实例变量赋值时，是否会触发 `KVO`?
### 9.`Delegate`通常用什么关键字修饰？为什么？
### 10`通知` 和 `代理` 有什么区别？各自适应的场景？
### 11.`__block` 的解释以及在 `ARC` 和 `MRC` 下有什么不同？
### 12.`Block` 的内存管理。
### 13.`Block` 自动截取变量。
### 14.`Block` 处理循环引用。
### 15.`Block` 有几种类型？分别是什么？

## 8.数据存储
### 1.Sqlite3 （不同版本的APP，数据库结构变化了，如何处理? ）
### 2.FMDB (`Sqlite3` 的封装)
### 3.Realm
### 4.NSKeyArchieve
### 5.Preperfence
### 6.Plist
### 7.CoreDate
### 8.Keychain
### 9.UIPasteBoard(感谢 lilingyu0620 同学提醒)
### 10.FoundationDB

## 9.iOS设计模式

### 1.编程中的六大设计原则？ 
### 2.如何设计一个图片缓存框架？ 
### 3.如何设计一个时长统计框架？ 
### 4.类工厂模式
### 5.外观模式
### 6.中介者模式
### 7.访问者模式
### 8.装饰模式 
### 9.观察者模式
### 10.责任链模式
### 11.命令模式
### 12.适配器模式
### 13.桥接模式
### 14.代理委托模式
### 15.单例模式


## 10.音频处理

## 11.视频处理

## 12.图像处理
* 1.图像的压缩、解压。

## 13.iOS 动画

## 14.蓝牙

## 15.ARKit

## 16.Core ML

## 17.代码管理、持续集成、项目托管
### 1.Git
* 1.`git pull` 和 `git fetch` 的区别？
* 2.`git merge` 和 `git rebase` 的区别？ 

### 2.Svn
### 3.CocoaPods
* 1.说一下 `CocoaPods` 的原理？
* 2.如何让自己写的框架支持 `CocoaPods`？
* 3.`pod update` 和 `pod install` 有什么区别？
* 4.`Podfile.lock` 文件起什么作用？
* 5.如何集成本地私有库？
* 6.如何集成远程私有库 ？

### 4.Carthage
### 5.Fastlane
### 6.Jenkins
### 7.fir.im
### 8.蒲公英
### 9.TestFlight

## 18.数据安全及加密
### 1.RSA非对称加密
### 2.AES对称加密
### 3.DES加密
### 4.Base64加密
### 5.MD5加密
### 6.简述 `SSL` 加密的过程用了哪些加密方法，为何这么作？
### 7.是否了解 `iOS` 的签名机制？
### 8.如何对 `APP` 进行重签名？

## 19.源代码阅读
### 1.YYKit
### 2.SDWebImage
### 3.AFNetworking
### 4.SVProgressHub 
### 5.Texture（ASDK）

## 20.iOS逆向及安全

## 21.性能优化
### 1.如何提升 `tableview` 的流畅度？
### 2.如何使用 `Instruments` 进行性能调优？(Time Profiler、Zombies、Allocations、Leaks)
### 3.如何优化 `APP` 的启动时间？（感谢 @静待海棠花开 的提醒）
### 4.如何对 `APP` 进行内存、电量、网络流量的优化？（感谢 @静待海棠花开 的提醒）
### 5.如何有效降低 `APP` 包的大小？
### 6.日常如何检查内存泄露？
### 7.能不能说一下物理屏幕显示的原理？
### 8.解释一下什么是屏幕卡顿、掉帧？该如何避免？
### 9.什么是 `离屏渲染`？什么情况下会触发？该如何应对？

## 22.调试技巧 & 软件使用
### 1.`LLDB` 调试。
### 2.断点调试。
### 3.`NSAssert` 的使用。
### 4.`Charles` 的使用。
### 5.`Reveal` 的使用。

## 23.扩展问题
### 1.无痕埋点
### 2.APM（应用程序性能监测）
### 3.Hot Patch（热修补）
### 4.崩溃的处理

## 24.其他问题
### 1.`UIView` 和 `CALayer` 是什么关系？
### 2.`Bounds` 和 `Frame` 的区别?
### 3.`nil`、`NIL`、`NSNULL` 有什么区别？
### 4.如何实现一个线程安全的 `NSMutableArray`?
### 5.如何定义一台 `iOS` 设备的唯一性?
### 6.如何高性能的画一个圆角？
### 7.`load` 和 `Initialize` 的区别?
### 8.`Designated Initializer`的规则？
### 9.`App` 编译过程有了解吗？
### 10.`JS` 和 `Native` 交互。
### 11.使用 `atomic` 一定是线程安全的吗？
### 12.`LoadView`方法了解吗？
### 13.说一下对 `APNS` 的认识？
### 14.实现 `isEqual` 和 `hash` 方法时要注意什么？
### 15.`UIButton` 的父类是什么？`UILabel` 的父类又是什么？
### 16.实现一个控件，可以浮在任意界面的上层并支持拖动？
### 17.解释一下 `copy` 关键字涉及的方方面面，说的越全越好。
### 18.说一下控制器 `View` 的生命周期，一旦收到内存警告会如何处理？
### 19.简述事件传递、事件响应机制。
### 20.说一下对 `Super` 关键字的理解。
### 21.了解 `逆变` 和 `协变` 吗？
### 22.`@synthesize` 和 `@dynamic` 分别有什么作用？
### 23.`Obj-C` 中的反射机制了解吗？
### 24.`atomic` 修饰的属性是绝对安全的吗？为什么？
### 25.`id` 和 `instanceType` 有什么区别？



## 25.计算题
1.**输出如下的计算结果**

```objc
int a=5,b;
b=(++a)+(++a);
```

## 26.开放性问题

### 1.你最近在业余时间研究那些技术点？可不可以分享一下你的心得？
### 2.你对自己未来的职业发展有什么想法？有没有对自己做过职业规划？
### 3.和同事产生矛盾（包括意见分歧），你一般怎么解决？
### 4.能不能说一下你的业余精力都花在什么方面，或者介绍一下你的爱好？
### 5.学习技术知识通常通过哪些途径？
### 6.遇到疑难问题一般怎么解决？能不能说一个你印象颇深的技术难点，后来怎么解决的？
