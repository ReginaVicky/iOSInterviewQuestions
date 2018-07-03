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

- 1.字符串反转 
- 2.链表反转
- 3.有序数组合并
- 4.Hash 算法
- 5.查找两个子视图的共同父视图
- 6.无序数组中的中位数
- 7.两数之和为特定值
- 补充：插入排序

## 1.iOS 内存管理
- 1.[讲一下 `iOS` 内存管理的理解？(三种方案的结合)](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博@Liberalisman面试知识点总结》/03《微博@Liberalisman面试知识点总结》.md#1讲一下-ios-内存管理的理解三种方案的结合) 
- 2.[使用自动引用计（`ARC`）数应该遵循的原则?](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博@Liberalisman面试知识点总结》/03《微博@Liberalisman面试知识点总结》.md#2使用自动引用计arc数应该遵循的原则) 
- 3.[`ARC` 自动内存管理的原则?](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#3arc-自动内存管理的原则)
- 4.[访问 `__weak` 修饰的变量，是否已经被注册在了 `@autoreleasePool` 中？为什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#4访问-__weak-修饰的变量是否已经被注册在了-autoreleasepool-中为什么)
- 5.[`ARC` 的 `retainCount` 怎么存储的？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#5arc-的-retaincount-怎么存储的)
- 6.[简要说一下 `@autoreleasePool` 的数据结构？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#6简要说一下-autoreleasepool-的数据结构)
- 7.[`__weak` 和 `_Unsafe_Unretain` 的区别？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#7__weak-和-_unsafe_unretain-的区别)
- 8.[为什么已经有了 `ARC` ,但还是需要 `@AutoreleasePool` 的存在？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#8为什么已经有了-arc-但还是需要-autoreleasepool-的存在)
- 9.[`__weak` 属性修饰的变量，如何实现在变量没有强引用后自动置为 `nil`](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#9__weak-属性修饰的变量如何实现在变量没有强引用后自动置为-nil)
- 10.[说一下对 `retain`,`copy`,`assign`,`weak`,`_Unsafe_Unretain` 关键字的理解。](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#10说一下对-retaincopyassignweak_unsafe_unretain-关键字的理解)
- [补充：简述下列属性的作用：readwrite、readonly、assign、retain、copy、nonatomic、weak、strong](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博@Liberalisman面试知识点总结》/03《微博@Liberalisman面试知识点总结》.md#补充简述下列属性的作用readwritereadonlyassignretaincopynonatomicweakstrong)
- 11.[`ARC` 在编译时做了哪些工作？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#11arc-在编译时做了哪些工作)
- 12.[`ARC` 在运行时做了哪些工作？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#12arc-在运行时做了哪些工作)
- 13.[函数返回一个对象时，会对对象 `autorelease` 么？为什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#13函数返回一个对象时会对对象-autorelease-么为什么)
- 14.[说一下什么是 `悬垂指针`？什么是 `野指针`?](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#14说一下什么是-悬垂指针什么是-野指针)
- 15.[内存管理默认的关键字是什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#15内存管理默认的关键字是什么)
- 16.[内存中的5大区分别是什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#16内存中的5大区分别是什么) 
- 17.[是否了解 `深拷贝` 和 `浅拷贝` 的概念，集合类深拷贝如何实现？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#17是否了解-深拷贝-和-浅拷贝-的概念集合类深拷贝如何实现)
- 18.[`BAD_ACCESS` 在什么情况下出现? ](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#18bad_access-在什么情况下出现)
- 19.[讲一下 `@dynamic` 关键字？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#19讲一下-dynamic-关键字)
- 20.[`@autoreleasrPool` 的释放时机？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#20autoreleasrpool-的释放时机)
- 21.[`retain`、`release` 的实现机制？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#21retainrelease-的实现机制)
- [补充：在OC里 `alloc` 和 `retain` 语义相反的方法是？]()
- [补充：`realease`作用是什么和 `autorelease` 有什么区别？]()
- 22.[能不能简述一下 `Dealloc` 的实现机制？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#22能不能简述一下-dealloc-的实现机制)


## 2.Runtime
- 1.[实例对象的数据结构？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#1实例对象的数据结构)
- 2.[类对象的数据结构？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#2类对象的数据结构)
- 3.[元类对象的数据结构?](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#3元类对象的数据结构)
- 4.[`Category` 的实现原理？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#4category-的实现原理)
- 5.[如何给 `Category` 添加属性？关联对象以什么形式进行存储？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#5如何给-category-添加属性关联对象以什么形式进行存储)
- 6.[`Category` 有哪些用途？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#6category-有哪些用途)
- 7.[`Category` 和 `Extension` 有什么区别？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#7category-和-extension-有什么区别)
- 8.[说一下 `Method Swizzling`? 说一下在实际开发中你在什么场景下使用过?](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#8说一下-method-swizzling-说一下在实际开发中你在什么场景下使用过)
- 9.[如何实现动态添加方法和属性？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#9如何实现动态添加方法和属性)
- 10.[说一下对 `isa` 指针的理解， 对象的`isa` 指针指向哪里？`isa` 指针有哪两种类型？（注意区分不同对象）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#10说一下对-isa-指针的理解-对象的isa-指针指向哪里isa-指针有哪两种类型注意区分不同对象) 
- 11.[`Obj-C` 中的类信息存放在哪里？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#11obj-c-中的类信息存放在哪里)
- 12.[一个 `NSObject` 对象占用多少内存空间？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#12一个-nsobject-对象占用多少内存空间)
- 13.[说一下对 `class_rw_t` 的理解？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#13说一下对-class_rw_t-的理解)
- 14.[说一下对 `class_ro_t` 的理解？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#14说一下对-class_ro_t-的理解)
- 15.[说一下 `Runtime` 消息解析。](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#15说一下-runtime-消息解析)
- 16.[说一下 `Runtime` 消息转发。](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#16说一下-runtime-消息转发)
- 17.[如何运用 `Runtime` 字典转模型？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#17如何运用-runtime-字典转模型)
- 18.[如何运用 `Runtime` 进行模型的归解档？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#18如何运用-runtime-进行模型的归解档)
- 19.[在 `Obj-C` 中为什么叫发消息而不叫函数调用？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#19在-obj-c-中为什么叫发消息而不叫函数调用)
- 20.[说一下对 `runtime` 的理解。（主要讲一下消息机制，是对上述的总结）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#20说一下对-runtime-的理解主要讲一下消息机制是对上述的总结)
- 21.[说一下 `Runtime` 的方法缓存？存储的形式、数据结构以及查找的过程？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#21说一下-runtime-的方法缓存存储的形式数据结构以及查找的过程)
- 22.[是否了解 `Type Encoding`? ](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#22是否了解-type-encoding)


## 3.Runloop
- 1.[`Runloop` 和线程的关系？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#1runloop-和线程的关系) 
- 2.[讲一下 `Runloop` 的 `Mode`?(越详细越好)](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#2讲一下-runloop-的-mode越详细越好) 
- 3.[讲一下 `Observer` ？（Mode中的重点）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#3讲一下-observer-mode中的重点) 
- 4.[讲一下 `Runloop` 的内部实现逻辑？（运行过程）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#4讲一下-runloop-的内部实现逻辑运行过程) 
- 5.[你所知的哪些三方框架使用了 `Runloop`?（AFNetworking、Texture 等）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#5你所知的哪些三方框架使用了-runloopafnetworkingtexture-等)
- 6.[`autoreleasePool` 在何时被释放？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#6autoreleasepool-在何时被释放) 
- 7.[解释一下 `事件响应` 的过程？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#7解释一下-事件响应-的过程) 
- 8.[解释一下 `手势识别` 的过程？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#8解释一下-手势识别-的过程) 
- 9.[解释一下 `GCD` 在 `Runloop` 中的使用？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#9解释一下-gcd-在-runloop-中的使用) 
- 10.[解释一下 `NSTimer`，以及 `NSTimer` 的循环引用。](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#10解释一下-nstimer以及-nstimer-的循环引用) 
- 11.[`AFNetworking` 中如何运用 `Runloop`? ](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#11afnetworking-中如何运用-runloop)
- 12.[`PerformSelector` 的实现原理？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#12performselector-的实现原理)
- 13.[利用 `runloop` 解释一下页面的渲染的过程？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#13利用-runloop-解释一下页面的渲染的过程)
- 14.[如何使用 `Runloop` 实现一个常驻线程？这种线程一般有什么作用？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#14如何使用-runloop-实现一个常驻线程这种线程一般有什么作用)
- 15.[为什么 `NSTimer` 有时候不好使？（不同类型的Mode）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#15为什么-nstimer-有时候不好使不同类型的mode)
- 16.[`PerformSelector:afterDelay:`这个方法在子线程中是否起作用？为什么？怎么解决？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#16performselectorafterdelay这个方法在子线程中是否起作用为什么怎么解决)
- 17.[什么是异步绘制？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/03《微博%40Liberalisman面试知识点总结》/03《微博%40Liberalisman面试知识点总结》.md#17什么是异步绘制)


## 4.网络
- 1.[`NSUrlConnect`相关知识。]()
- 2.[`NSUrlSession`相关知识。]()
- 3.[`Http` 和 `Https` 的区别？为什么更加安全？]()
- 4.[`Http`的请求方式有哪些？`Http` 有什么特性？]()
- 5.[解释一下 `三次握手` 和 `四次挥手`？解释一下为什么是`三次握手` 又为什么是 `四次挥手`？]()
- 6.[`GET` 和 `POST` 请求的区别？]()
- 7.[`HTTP` 请求报文 和 响应报文的结构？]()
- 8.[什么是 `Mimetype` ? ]()
- 9.[数据传输的加密过程？]() 
- 10.[说一下 `TCP/IP` 五层模型的协议? ]()
- 11.[说一下 `OSI` 七层模型的协议?]() 
- 12.[`大文件下载` 的功能有什么注意点？]() 
- 13.[`断点续传` 功能该怎么实现？]() 
- 14.[封装一个网络框架有哪些注意点？]()
- 15.[`Wireshark`、`Charles`、`Paw` 等工具会使用吗？]()
- 16.[`NSUrlProtocol`用过吗？用在什么地方了？]()
- 17.[如何在测试过程中 `MOCK` 各种网络环境？]() 
- 18.[`DNS` 的解析过程？网络的 `DNS` 优化。]() 
- 19.[`Post`请求体有哪些格式？]()
- 20.[网络请求的状态码都大致代表什么意思？]()
- 21.[抓包软件 `Charles` 的原理是什么？说一下中间人攻击的过程。]()
- 22.[如何判断一个请求是否结束？]()
- 23.[`SSL` 传输协议？说一下 `SSL` 验证过程？]()
- 24.[解释一下 `Http` 的持久连接？]()
- 25.[说一下传输控制协议 - `TCP` ?]()
- 26.[说一下用户数据报协议 - `UDP` ?]() 
- 27.[谈一谈网络中的 `session` 和 `cookie`?]() 
- 补充：使用异步请求的方式抓取一个网站的内容，请考虑超时，状态码的异常情况（请用原生API或者Socket/Cocoa Socket）

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

- 1.编程中的六大设计原则？ 
- 2.如何设计一个图片缓存框架？ 
- 3.如何设计一个时长统计框架？ 
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
- 补充：在OC中对象方法的几种访问权限，分别是什么？
- 补充：列出 #import 和 #include 的区别，另外什么时候使用@class？
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
- 补充：简述Xcode7和Xcode8的异同
- 补充：描述iOS 10的一些新特性（包括系统和开发环境）



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
- 7.作为开发苹果应用者有多长时间，拥有哪些苹果设备？
- 8.平时你经常访问哪些技术类网址
- 9.为什么选择iOS开发，你对它的前景和本身有什么想法？请简要回答。
- 10.你有自己的开源项目吗，用什么托管的代码？

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

* ARC规则：
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

* 采用散列表（引用计数表）来管理引用计数。
![image](https://upload-images.jianshu.io/upload_images/131615-d1212b1150b575e7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

GNUstep将引用计数保存在对象占用内存块头部的变量中，而苹果的实现，则是保存在引用计数表的记录中。
* 通过内存卡头部管理引用计数的好处如下：
    - 少量代码即可完成
    - 能够统一管理引用计数用内存块与对象用内存块
* 通过引用计数表管理引用计数的好处如下：
    - 对象用内存块的分配无需考虑内存块头部
    - 引用计数表各记录中存有内存块地址，可从各个记录中追溯到各对象的内存块
* 即使出现故障导致对象占用的内存块损坏，但只要引用计数表没有被破坏，就能够确认各内存块的位置
![image](https://upload-images.jianshu.io/upload_images/131615-6ebbb4f2275a7362.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

### 6.简要说一下 `@autoreleasePool` 的数据结构？ 

* 系统通过一个栈来管理所有的自动释放池，每当创建了一个新的自动释放池，系统就会把它压入栈顶，并且传入一个哨兵对象,将哨兵对象插入hotPage，这里分三种情况
    - 若hotPage未满，则直接插入哨兵对象，
    - 要是满了，新建一个NSAutoreleasePoolPage，并将其作为hotPage，然后将哨兵对象插入
    - 如果没有NSAutoreleasePoolPage,则新建一个NSAutoreleasePoolPage，并将其作为hotPage，插入哨兵对象，注意。这里的hotPage是没有父节点的。
* 每当有一个自动释放池要被释放的时候，哨兵对象就会作为参数被传入，找到该哨兵对象所在的位置后，将所有晚于哨兵对象的autorelease弹出，并对他们做一次release，然后将next指针一到合适的位置。
* 首先我们去可以查看一下，clang 转成 c++ 的 autoreleasepool 的源码：

```
extern "C" __declspec(dllimport) void * objc_autoreleasePoolPush(void);
extern "C" __declspec(dllimport) void objc_autoreleasePoolPop(void *);
struct __AtAutoreleasePool {
  __AtAutoreleasePool() {atautoreleasepoolobj = objc_autoreleasePoolPush();}
  ~__AtAutoreleasePool() {objc_autoreleasePoolPop(atautoreleasepoolobj);}
  void * atautoreleasepoolobj;
};

```
可以发现objc_autoreleasePoolPush() 和 objc_autoreleasePoolPop() 这两个方法。

* 再看一下runtime 中 Autoreleasepool 的结构，通过阅读源码可以看出 Autoreleasepool 是一个由 AutoreleasepoolPage 双向链表的结构，其中 child 指向它的子 page，parent 指向它的父 page。

![image](https://upload-images.jianshu.io/upload_images/1197643-96db24a6be7d1796.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

* 并且每个 AutoreleasepoolPage 对象的大小都是 4096 个字节。

```
#define PAGE_MAX_SIZE           PAGE_SIZE
#define PAGE_SIZE       I386_PGBYTES
#define I386_PGBYTES        4096        /* bytes per 80386 page */

```
* AutoreleasepoolPage 通过压栈的方式来存储每个需要自动释放的对象。

```
//入栈方法
    static inline void *push() 
    {
        id *dest;
        if (DebugPoolAllocation) {
            // Each autorelease pool starts on a new pool page.
            //在 Debug 情况下每一个自动释放池 都以一个新的 poolPage 开始
            dest = autoreleaseNewPage(POOL_BOUNDARY);
        } else {
//正常情况下，调用 push 方法会先插入一个 POOL_BOUNDARY 标志位
            dest = autoreleaseFast(POOL_BOUNDARY);
        }
        assert(dest == EMPTY_POOL_PLACEHOLDER || *dest == POOL_BOUNDARY);
        return dest;
    }

```

### 7.`__weak` 和 `_Unsafe_Unretain` 的区别？

__weak，当释放指针指向的对象时，该对象的指针将转换为nil，这是比较安全的行为。
__unsafe_unretain，正如其名称隐藏的含义，尽管释放指针指向的对象时，该指针将继续指向原来的内存。不会置为nill，造成了垂悬指针。这将会导致应用崩溃，所以是不安全的。



### 8.为什么已经有了 `ARC` ,但还是需要 `@AutoreleasePool` 的存在？

* 自动释放池可以延长对象的声明周期，如果一个事件周期很长，比如有一个很长的循环逻辑，那么一个临时变量可能很长时间都不会被释放，一直在内存中保留，那么内存的峰值就会一直增加，但是其实这个临时变量是我们不再需要的。这个时候就通过创建新的自动释放池来缩短临时变量的生命周期来降低内存的峰值。
* 注意：临时生成大量对象,一定要将自动释放池放在for循环里面，要释放在外面，就会因为大量对象得不到及时释放，而造成内存紧张，最后程序意外退出

### 9.`__weak` 属性修饰的变量，如何实现在变量没有强引用后自动置为 `nil`？ 

* 都知道，weak是弱引用，所引用对象的计数器不会加一，并在引用对象被释放的时候自动被设置为nil。通常用于解决循环引用问题。
* 其实质是：Runtime维护了一个weak表，用于存储指向某个对象的所有weak指针。weak表其实是一个hash（哈希）表，Key是所指对象的地址，Value是weak指针的地址（这个地址的值是所指对象的地址）数组。
* weak 的实现原理可以概括一下三步：
    - 初始化时：runtime会调用objc_initWeak函数，初始化一个新的weak指针指向对象的地址。
    - 添加引用时：objc_initWeak函数会调用 objc_storeWeak() 函数， objc_storeWeak() 的作用是更新指针指向，创建对应的弱引用表。
    - 释放时，调用clearDeallocating函数。clearDeallocating函数首先根据对象地址获取所有weak指针地址的数组，然后遍历这个数组把其中的数据设为nil，最后把这个entry从weak表中删除，最后清理对象的记录。
* 当weak引用指向的对象被释放时，其基本流程如下：
    - 调用objc_release
    - 因为对象的引用计数为0，所以执行dealloc
    - 在dealloc中，调用了_objc_rootDealloc函数
    - 在_objc_rootDealloc中，调用了object_dispose函数
    - 调用objc_destructInstance
    - 最后调用objc_clear_deallocating
 * objc_clear_deallocating该函数的动作如下：
    - 从weak表中获取废弃对象的地址为键值的记录
    - 将包含在记录中的所有附有 weak修饰符变量的地址，赋值为nil
    - 将weak表中该记录删除
    - 从引用计数表中删除废弃对象的地址为键值的记录
 其实，最终是使用了迭代器来取weak表的value，然后调用weak_clear_no_lock,然后查找对应的value，将该weak指针置空。

### 10.说一下对 `retain`,`copy`,`assign`,`weak`,`_Unsafe_Unretain` 关键字的理解。 

* assign： 简单赋值，不更改索引计数 ,主要用于修饰基本数据类型，存储在栈中，内存不用程序员管理。
* copy:建立一个引用计数为1的对象，然后释放旧对象 ,像NSString是内容拷贝,但是如果copy的是一个NSArray，copy是指向array中相对应元素的指针。
* strong：表示指向并持有该对象，在堆中复制一个值一样的对象， 旧的值release掉，指向新的复制的对象，与retain不同之处在于copy会在内存中创建一个与旧对象相同的对象，然后release旧的，重新指向这个新的。其修饰对象的引用计数会加1。该对象只要引用计数不为0就不会被销毁。当然可以通过将变量强制赋值 nil 来进行销毁。
* weak：指向但是并不持有该对象，引用计数也不会加1。在 Runtime 中对该属性进行了相关操作，无需处理，可以自动销毁。weak用来修饰对象，多用于避免循环引用的地方。weak 不可以修饰基本数据类型。
*_unsafe_unretain:类似于weak，但是当对象被释放后，指针已然保存着之前的地址，被释放后的地址变为僵尸对象，访问被释放的地址就会出现问题，所以说他是不安全的。
* _strong:表示引用为强引用。对应在定义propery时的strong。所有对象只有当没有任何一个强引用指向时，才会被释放。
          注意：如果在声明引用时不加修饰符，那么引用将默认为强引用。当需要释放强引用指向的对象时，需要将强引用置为nil。
* _weak:表示引用为弱引用。对应在定义property时用的"weak"。弱引用不会影响对象的释放，即只要对象没有任何强引用指向，即使有100个弱引用对象指向也没用，该对象依然会被释放。不过好在，对象在被释放的同时，指向它的弱引用会自动被置nil，这个技术叫zeroing weak pointer。这样有效得防止无效指针、野指针的产生。__weak一般用在delegate关系中防止循环引用或者用来修饰指向由Interface Builder编辑与生成的UI控件。
* _autoreleasing:表示在autorelease pool中自动释放对象的引用，和MRC时代autorelease的用法相同。定义property时不能使用这个修饰符，任何一个对象的property都不应该是autorelease型的。

### 补充：简述下列属性的作用：readwrite、readonly、assign、retain、copy、nonatomic、weak、strong

* readwrite:可读写属性，需要生成getter方法和setter方法;
* readonly:只读属性，只会生成getter方法 不会生成setter方法 ,不希望属性在类外改变;  
* assign:简单赋值，setter方法将传入参数赋值给实例变量;仅设置变量时;不更改索引计数 ,主要用于修饰基本数据类型，存储在栈中，内存不用程序员管理。为了解决原类型和循环引用问题。
* retain:setter方法对参数进行release旧值，再retain新值，就是setter方法将传入参数先保留,再赋值,
* copy:建立一个引用计数为1的对象，然后释放旧对象 ,像NSString是内容拷贝,但是如果copy的是一个NSArray，copy是指向array中相对应元素的指针。
* nonatomic:非原子性访问，不加同步，多线程并发访问会提高性能。注意，如果不加此属性，则默认是两个访问方法都为原子型事务访问。锁被加到所属对象实例级
* weak:weak其实类似于assign，叫弱引用，也是不增加引用计数。一般只有在防止循环引用时使用，比如父类引用了子类，子类又去引用父类。IBOutlet、Delegate一般用的就是weak，这是因为它们会在类外部被调用，防止循环引用。
* strong:相对的，strong就类似与retain了，叫强引用，会增加引用计数，类内部使用的属性一般都是strong修饰的，现在ARC已经基本替代了MRC，所以我们最常见的就是strong了。


### 11.`ARC` 在编译时做了哪些工作？ 

当我们编译源码的时候，编译器会分析源码中每个对象的生命周期，然后基于这些对象的生命周期，来添加相应的引用计数操作代码,在适当的位置插入 retain，release;

### 12.`ARC` 在运行时做了哪些工作？ 

* 主要是指 weak 关键字。weak 修饰的变量能够在引用计数为0 时被自动设置成 nil，显然是有运行时逻辑在工作的。
* 为了保证向后兼容性，ARC 在运行时检测到类函数中的 autorelease 后紧跟其后 retain，此时不直接调用对象的 autorelease 方法，而是改为调用 objc_autoreleaseReturnValue。 objc_autoreleaseReturnValue 会检视当前方法返回之后即将要执行的那段代码，若那段代码要在返回对象上执行 retain 操作，则设置全局数据结构中的一个标志位，而不执行 autorelease 操作，与之相似，如果方法返回了一个自动释放的对象，而调用方法的代码要保留此对象，那么此时不直接执行 retain ，而是改为执行 objc_retainAoutoreleasedReturnValue函数。此函数要检测刚才提到的标志位，若已经置位，则不执行 retain 操作，设置并检测标志位，要比调用 autorelease 和retain更快。

### 13.函数返回一个对象时，会对对象 `autorelease` 么？为什么？

* 会
* 如果一个方法需要返回一个新建的对象，这时，如果方法内部写 release来释放对象,就会将对象立即释放而返回一个空对象;其次，调用者也不会主动释放该对象的,因为调用者遵循“谁申请,谁释放”的原则。那么这个时候,就发生了内存泄露。为了解决这个问题， 就会使用autorelease,既能确保对象能正确释放,又能返回有效的对象。autorelease 实际上只是把对release 的调用延迟了,对于每一个Autorelease,系统只是把该Object 放入了当前的Autorelease pool 中,当该pool被释放时,该pool 中的所有Object 会被调用Release。

### 14.说一下什么是 `悬垂指针`？什么是 `野指针`?

* 垂悬指针：指向曾经存在的对象，但该对象已经不再存在了，内存已经被释放了，但是指针还存在，此类指针称为垂悬指针。
    - 解决策略：引用智能指针可以防止垂悬指针出现。一般是把指针封装到一个称之为智能指针类中，这个类中另外还封装了一个使用计数器，对指针的复制等操作将导致该计数器的值加1，对指针的delete操作则会减1，值为0时，指针为NULL。
* 野指针：“野指针”不是NULL指针，是指向“垃圾”内存（不可用内存）的指针。
    - 造成野指针的情况：
        - 指针变量没有被初始化。任何指针变量刚被创建时不会自动成为NULL指针，它的缺省值是随机的，它会乱指一气。所以，指针变量在创建的同时应当被初始化，要么将指针设置为NULL，要么让它指向合法的内存。
        - 指针被free或者delete之后，没有置为NULL，让人误以为p是个合法的指针。
        - 指针操作超越了变量的作用范围。

### 15.内存管理默认的关键字是什么？

* marc：atomic、readwrite、retain；
* arc：atomic、readwrite、strong；
* 基本数据类型时：assign；

### 16.内存中的5大区分别是什么？ 

![image](https://upload-images.jianshu.io/upload_images/1494773-fc9423bca3512c6e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/644)
* 栈区：由编译器自动分配并释放，存放函数的参数值，局部变量等。栈是系统数据结构，对应线程/进程是唯一的。
    - 优点是快速高效
    - 缺点是有限制，数据不灵活。［先进后出］
    - 栈空间分静态分配 和动态分配两种。
    - 静态分配是编译器完成的，比如自动变量(auto)的分配。
    - 动态分配由alloca函数完成。
    - 栈的动态分配无需释放(是自动的)，也就没有释放函数。
    - 为可移植的程序起见，栈的动态分配操作是不使用的一般
    - 存储每一个函数在执行的时候都会向操作系统索要资源，栈区就是函数运行时的内存，栈区中的变量由编译器负责分配和释放，内存随着函数的运行分配，随着函数的结束而释放，由系统自动完成。
    - 注意：只要栈的剩余空间大于所申请空间，系统将为程序提供内存，否则将报异常提示栈溢出。
    - 栈是向低地址扩展的数据结构，是一块连续的内存的区域。是栈顶的地址和栈的最大容量是系统预先规定好的，栈的大小是一个编译时就确定的常数 ,如果申请的空间超过栈的剩余空间时，将提示overflow。因此，能从栈获得的空间较小。
    - 内存由系统自动分配,速度快,不会产生内存碎片
* 堆区
    - 堆区由程序员分配和释放，如果程序员不释放，程序结束时，可能会由操作系统回收 ，比如在ios 中 alloc 都是存放在堆中。
    - 优点是灵活方便，数据适应面广泛
    - 缺点是效率有一定降低。［顺序随意］
    - 堆是函数库内部数据结构，不一定唯一。
        - 不同堆分配的内存无法互相操作。
        - 堆空间的分配总是动态的
        - 虽然程序结束时所有的数据空间都会被释放回系统，但是精确的申请内存，释放内存匹配是良好程序的基本要素。
    - 操作系统有一个记录空闲内存地址的链表。
    - 当系统收到程序的申请时，会遍历该链表，寻找第一个空间大于所申请空间的堆结点，然后将该结点从空闲结点链表中删除，并将该结点的空间分配给程序。
    - 由于找到的堆结点的大小不一定正好等于申请的大小，系统会自动的将多余的那部分重新放入空闲链表中
    - 堆是向高地址扩展的数据结构，是不连续的内存区域。这是由于系统是用链表来存储的空闲内存地址的，自然是不连续的，而链表的遍历方向是由低地址向高地址。堆的大小受限于计算机系统中有效的虚拟内存。由此可见，堆获得的空间比较灵活，也比较大。
    - 有alloc分配的内存,速度较慢,会产生内存碎片,但是使用方便
* 全局区(静态区)
    - 全局变量和静态变量的存储是放在一起的，初始化的全局变量和静态变量存放在一块区域，未初始化的全局变量和静态变量在相邻的另一块区域，程序结束后由系统释放。
* 常量区
    - 常量区,存放常量字符串,程序结束后由系统释放
* 程序代码区(方法区)
    - 存放函数的二进制代码

### 17.是否了解 `深拷贝` 和 `浅拷贝` 的概念，集合类深拷贝如何实现？

* 对象拷贝有两种方式：浅复制和深复制。顾名思义，浅复制，并不拷贝对象本身，仅仅是拷贝指向对象的指针；深复制是直接拷贝整个对象内存到另一块内存中。
 ![image](http://7s1ssm.com1.z0.glb.clouddn.com/image_note50592_1.png)
* 再简单些说：浅复制就是指针拷贝；深复制就是内容拷贝。
* 集合类深拷贝，集合的深复制有两种方法。
    - 可以用 initWithArray:copyItems: 将第二个参数设置为YES即可深复制，如
 ```
NSDictionary shallowCopyDict = [[NSDictionary alloc] initWithDictionary:someDictionary copyItems:YES];
```
如果你用这种方法深复制，集合里的每个对象都会收到 copyWithZone: 消息。如果集合里的对象遵循 NSCopying 协议，那么对象就会被深复制到新的集合。如果对象没有遵循 NSCopying 协议，而尝试用这种方法进行深复制，会在运行时出错。copyWithZone: 这种拷贝方式只能够提供一层内存拷贝(one-level-deep copy)，而非真正的深复制。
    - 第二个方法是将集合进行归档(archive)，然后解档(unarchive)，
```
NSArray *trueDeepCopyArray = [NSKeyedUnarchiver unarchiveObjectWithData:[NSKeyedArchiver archivedDataWithRootObject:oldArray]];
```

[iOS 集合的深复制与浅复制](https://www.zybuluo.com/MicroCai/note/50592)

### 18.`BAD_ACCESS` 在什么情况下出现? 

* 访问了野指针的时候，比如一个已经释放的对象执行了release、访问已经释放对象的成员变量或者发消息。
* 死循环的时候也会。

### 19.讲一下 `@dynamic` 关键字？

* @dynamic这个关键词，通常是用不到的。
* 它与@synthesize的区别在于：
    - 使用@synthesize编译器会确实的产生getter和setter方法，而@dynamic仅仅是告诉编译器这两个方法在运行期会有的，无需产生警告。
* 假设有这么个场景，B类，C类分别继承A类，A类实现某个协议（@protocol），协议中某个属性( somePropety )我不想在A中实现，而在B类，C类中分别实现。如果A中不写任何代码，编译器就会给出警告：

“use @synthesize, @dynamic or provide a method implementation"

这时你给用@dynamic somePropety; 编译器就不会警告，同时也不会产生任何默认代码。

### 20.`@autoreleasrPool` 的释放时机？

* App启动后，苹果在主线程 RunLoop 里注册了两个 Observer，其回调都是 _wrapRunLoopWithAutoreleasePoolHandler()。
* 第一个 Observer 监视的事件是 Entry(即将进入Loop)，其回调内会调用 _objc_autoreleasePoolPush() 创建自动释放池。其 order 是 -2147483647，优先级最高，保证创建释放池发生在其他所有回调之前。
* 第二个 Observer 监视了两个事件： BeforeWaiting(准备进入休眠) 时调用_objc_autoreleasePoolPop() 和 _objc_autoreleasePoolPush() 释放旧的池并创建新池；Exit(即将退出Loop) 时调用 _objc_autoreleasePoolPop() 来释放自动释放池。这个 Observer 的 order 是 2147483647，优先级最低，保证其释放池子发生在其他所有回调之后。
* 在主线程执行的代码，通常是写在诸如事件回调、Timer回调内的。这些回调会被 RunLoop 创建好的 AutoreleasePool 环绕着，所以不会出现内存泄漏，开发者也不必显示创建 Pool 了。

### 21.`retain`、`release` 的实现机制？

### 补充：`realease`作用是什么和 `autorelease` 有什么区别？
### 补充：在OC里 `alloc` 和 `retain` 语义相反的方法是？

### 22.能不能简述一下 `Dealloc` 的实现机制？


## 2.Runtime
### 1.实例对象的数据结构？
### 2.类对象的数据结构？
### 3.元类对象的数据结构? 
### 4.`Category` 的实现原理？ 

* 无论我们有没有主动引入 Category 的头文件，Category 中的方法都会被添加进主类中。我们可以通过 - performSelector: 等方式对 Category 中的相应方法进行调用
* 文中类与分类代码如下
```
//类
@interface Person : NSObject
@property (nonatomic ,copy) NSString *presonName;
@end

@implementation Person
- (void)doSomeThing{
    NSLog(@"Person");
}
@end

```
```
// 分类
@interface Person(categoryPerson)
@property (nonatomic ,copy) NSString *categoryPersonName;
@end

@implementation Person(categoryPerson)
- (void)doSomeThing{
    NSLog(@"categoryPerson");
}
@end

```
* 分类的结构体
```
struct _category_t {
    const char *name;//类名
    struct _class_t *cls;//类
    const struct _method_list_t *instance_methods;//category中所有给类添加的实例方法的列表（instanceMethods）
    const struct _method_list_t *class_methods;//category中所有添加的类方法的列表（classMethods）
    const struct _protocol_list_t *protocols;//category实现的所有协议的列表（protocols）
    const struct _prop_list_t *properties;//category中添加的所有属性（instanceProperties）
};

struct category_t {
    const char *name; // 类名
    classref_t cls;   // 分类所属的类
    struct method_list_t *instanceMethods;  // 实例方法列表
    struct method_list_t *classMethods;     // 类方法列表
    struct protocol_list_t *protocols;      // 遵循的协议列表
    struct property_list_t *instanceProperties; // 属性列表

    // 如果是元类，就返回类方法列表；否则返回实例方法列表
    method_list_t *methodsForMeta(bool isMeta) {
        if (isMeta) {
            return classMethods;
        } else {
            return instanceMethods;
        }
    }

    // 如果是元类，就返回 nil，因为元类没有属性；否则返回实例属性列表，但是...实例属性
    property_list_t *propertiesForMeta(bool isMeta) {
        if (isMeta) {
            return nil; // classProperties;
        } else {
            return instanceProperties;
        }
    }
};
```
[ios 分类的实现原理](https://blog.csdn.net/sharpyl/article/details/78238814?locationNum=1&fps=1)

### 5.如何给 `Category` 添加属性？关联对象以什么形式进行存储？ 

* 使用Runtime中的关联对象
* 由于一些特殊的需要，我们可能要给现有的类添加一些新的方法，这个需求用继承也可以做到，但是会显得比较重，这时候就可以用Category来达到目的，创建一个已有类的Category，可以给这个类添加你需要的方法，在使用的时候，只需要import你创建的Category，在使用的时候还是使用原来的类，但是你会发现他支持你自己在Category中添加的方法。
* 我们看到的一些名为类似“UINavigationController+Cloudox.h”的文件就是类别了。
* 我们都知道用Category类别可以给一些已经存在的，比如系统的类添加方法，但是不能添加新属性，那怎么添加属性呢？一种直接的方法是继承，但如果只是为了添加一个属性就去做一次继承，还是有点重，这时候，就可以用关联对象的方法。
* 有两个相关的方法：
    - objc_setAssociatedObject 方法用来给类关联一个属性；
    - objc_getAssociatedObject 方法用来获取之前关联的属性。
* 比如说给自己这个类关联一个字符串：
```
// 关联对象
    static char associatedObjectKey;
    objc_setAssociatedObject(self, &associatedObjectKey, @"我就是要关联的字符串对象内容", OBJC_ASSOCIATION_RETAIN_NONATOMIC);
    NSString *theString = objc_getAssociatedObject(self, &associatedObjectKey);
    NSLog(@"关联对象：%@", theString);
```
我们先给self关联了一个字符串内容，然后通过get方法获取了关联的字符串内容，并输出。

从代码中其实也可以猜到各个参数的意思，self的参数就是要处理的类；associatedObjectKey 的参数其实就类似于key，用来标识区分你要关联的这个对象；第三个参数是要关联的对象；第四个参数是关联的策略，
* 当然，你也可以和类别一起用，创建两个方法用来关联和获取对象，比如下面这样：
```
//添加关联对象
- (void)addAssociatedObject:(id)object{
    objc_setAssociatedObject(self, @selector(getAssociatedObject), object, OBJC_ASSOCIATION_RETAIN_NONATOMIC);
}

//获取关联对象
- (id)getAssociatedObject{
    return objc_getAssociatedObject(self, _cmd);
}
```
这样就既能通过Category类别来添加方法，用一起顺便提供了对属性的添加了。
* 关联对象 以哈希表的格式，存储在一个全局的单例中。

### 6.`Category` 有哪些用途？ 

* 在不创建继承类的情况下实现对已有类的扩展。
* 简化类的开发工作(当一个类需要多个程序员协同开发的时候,Category可以将同一个类根据用途分别放在不同的源文件中,从而便于程序员独立开发相应的方法集合)。
* 将常用的相关的方法分组。
* 在没有源代码的情况下可以用来修复BUG。
* 模拟多继承（另外可以模拟多继承的还有protocol）
* 把framework的私有方法公开

### 补充：`Category`的优缺点？
* 好处
    - 可以将类的实现分散到多个不同的文件或者不同的框架中，方便代码的管理。也可以对框架提供类的扩展。（可以减少单个文件的体积，可以把不同的功能组织到不同的category里，可以由多个开发者共同完成一个类，可以按需加载想要的category）
    - 创建对私有方法的前向引用：如果其他类中的方法未实现，在你访问其他类的私有方法时编译器报错这时使用类别，在类别中声明这些方法（不必提供方法实现），编译器就不会再产生警告
    - 向对象添加非正式协议：创建一个NSObject的类别称为“创建一个非正式协议”，因为可以作为任何类的委托对象使用（声明私有方法）。
* 不足
    - category只能给某个已有的类扩充方法，不能扩充成员变量。
    - category中也可以添加属性，只不过@property只会生成setter和getter的声明，不会生成setter和getter的实现以及成员变量。
    - 如果category中的方法和类中原有方法同名，运行时会优先调用category中的方法。也就是，category中的方法会覆盖掉类中原有的方法。所以开发中尽量保证不要让分类中的方法和原有类中的方法名相同。避免出现这种情况的解决方案是给分类的方法名统一添加前缀。比如category_。
    - 如果多个category中存在同名的方法，运行时到底调用哪个方法由编译器决定，最后一个参与编译的方法会被调用。

### 7.`Category` 和 `Extension` 有什么区别？

* `Category`：类别是一种为现有的类添加新方法的方式。利用Objective-C的动态运行时分配机制，Category提供了一种比继承（inheritance）更为简洁的方法来对class进行扩展，无需创建对象类的子类就能为现有的类添加新方法，可以为任何已经存在的class添加方法，包括那些没有源代码的类。
* 类别的作用主要有三个：
    - 可以将类的实现分散到多个不同的文件或者不同的框架中，方便代码的管理。也可以对框架提供类的扩展（没有源码，不能修改）。
    - 创建对私有方法的前向引用：如果其他类中的方法未实现，在你访问其他类的私有方法时编译器报错这时使用类别，在类别中声明这些方法（不必提供方法实现），编译器就不会再产生警告
    - 向对象添加非正式协议：创建一个NSObject的类别称为“创建一个非正式协议”，因为可以作为任何类的委托对象使用。
* `Extension`：首先还是需要创建相关类的扩展，即方法的声明，然后在需要扩张的类中引入头文件，然后实现声明的方法。
* `Category` 和 `Extension` 的区别
    - 形式上看：extension 是匿名的category
    - extension中声明的方法需要在mainimplementation中实现，而category 不做强制要求
    - extension 可以添加属性、成员变量，而category 一般不可以。

### 补充：介绍一下`Category`（类别）、`Extension`（拓展）和继承，它们的区别是什么？优缺点分别是什么？

* `Category`
    - 当原有类的方法不够用时，这时候分类就出现了。分类就是对一个类的功能进行扩展,利用objective-c 的动态运行时分配机制，可以为现有类添加新方法。可以在分类中添加方法和成员变量，但是添加的成员变量不会自动生成setter和getter方法，需要在实现部分给出实现。
    - 作用
        - 可以将类的实现分散到多个不同的文件或者不同的框架中，方便代码的管理。也可以对框架提供类的扩展（没有源码，不能修改）。
        - 创建对私有方法的前向引用：如果其他类中的方法未实现，在你访问其他类的私有方法时编译器报错这时使用类别，在类别中声明这些方法（不必提供方法实现），编译器就不会再产生警告
        - 向对象添加非正式协议：创建一个NSObject的类别称为“创建一个非正式协议”，因为可以作为任何类的委托对象使用。       
    - 局限性
        - 分类只能增加方法,不能增加成员变量,但是可以通过运行时来给分类添加属性,
        - 如果分类和原来类出现同名的方法, 优先调用分类中的方法,原来类中的方法会被忽略,方法调用的优先级(从高到低) 分类(最后参与编译的分类优先),只要有分类就优先调用分类,不考虑与主类的编译顺序
        - 利用运行时来为分类添加属性
```
1、引入运行时头文件。
#import <objc/runtime.h>
```

```
2、在匿名分类或者头文件中添加属性。区别是：匿名分类中添加的是私有属性，只在本类中可以使用，类的实
例中不可以使用。头文件中添加的在类的实例中也可以使用。

//分类的头文件
@interface ClassName (CategoryName)
//我要添加一个实例也可以访问的变量所以就写在这里了
@property (nonatomic, strong) NSString *str;
@end

//匿名分类
@interface ClassName ()

@end

```
```
3、在实现里面写要添加属性的getter、setter方法

static void *strKey = &strKey;
@implementation ClassName (CategoryName) 

-(void)setStr:(NSString *)str  
{  
    objc_setAssociatedObject(self, &strKey, str, OBJC_ASSOCIATION_COPY);  
}  

-(NSString *)str  
{  
    return objc_getAssociatedObject(self, &strKey);  
}
@end

在setStr:方法中使用了一个objc_setAssociatedObject的方法，这个方法有四个参数，分别是：
1.源对象，
2.关联时的用来标记是哪一个属性的key（因为你可能要添加很多属性），
3.关联的对象
4.一个关联策略。
```
* `Extension`：
    - 是Category的一个特例，
    - 作用
        - 为一个类增加私有方法,属性或成员变量,也就是说
    - 局限性
        - 只能在本文件中被使用其名字为匿名(为空),并且新添加的方法一定要予以实现。(Category没有这个限制)
    - 实现
        - 第一种方法：通过延展来实现方法的私有,延展的头文件独立。这种方法不能实现真正的方法私有,当在别的文件中引入延展的头文件,那么在这个文件中定义的类的对象就可以直接调用在延展中定义所谓私有的方法
        - 第二种实现延展的方式：延展没有独立的头文件,在类的实现文件.m中声明和实现延展,这种方法可以很好的实现方法的私有,因为在OC中是不能引入.m的文件的
        - 第三种实现方法：私有的方式是在.m文件中的@implementation中直接实现在@interface中没有声明的方法,这样也可以很好的实现方法的私有,开发中经常用的方式。
    - Category和Extension区别
        - 形式上看：extension 是匿名的category
        - extension中声明的方法需要在implementation中实现，而category 不做强制要求
        - extension 可以添加属性、成员变量，而category 一般不可以。
        - 虽然有人说extension是一个特殊的category，也有人将extension叫做匿名分类，但是其实两者差别很大。
        - extension
            - 在编译器决议，是类的一部分，在编译器和头文件的@interface和实现文件里的@implement一起形成了一个完整的类。
            - 伴随着类的产生而产生，也随着类的消失而消失。
            - extension一般用来隐藏类的私有消息，你必须有一个类的源码才能添加一个类的extension，所以对于系统一些类，如nsstring，就无法添加类扩展
        - category
            - 是运行期决议的
            - 类扩展可以添加实例变量，分类不能添加实例变量
            - 原因：因为在运行期，对象的内存布局已经确定，如果添加实例变量会破坏类的内部布局，这对编译性语言是灾难性的。
* 继承：
    - 多个类具有相同的实例变量和方法时，考虑用继承。即子类可以继承父类的相同特性。
    - 作用
        - 在子类中新扩展的方法与原方法同名，但是还需要使用父类的实现要用继承。因为使用类别，会覆盖原类的实现，无法访问到原来的方法。
        - 扩展类的属性和实例变量，这个类别无法做到。
        - 子类可以继承类别中的方法。
    - 和Category的区别：
        - 类别是对方法的扩展，不能添加成员变量。继承可以在原来父类的成员变量的基础上，添加新的成员变量
        - 类别只能添加新的方法，不能修改和删除原来的方法。继承可以增加、修改和删除方法。
        - 类别不提倡对原有的方法进行重载。继承可以通过使用super对原来方法进行重载。
        - 类别可以被继承，如果一个父类中定义了类别，那么其子类中也会继承此类别。
        - 共同点：都是给一个类进行扩展


### 8.说一下 `Method Swizzling`? 说一下在实际开发中你在什么场景下使用过? 

* Method Swzzling，是指runtime的一个API方法,Method Swizzling本质上就是对IMP和SEL进行交换。
* Method Swizzing是发生在运行时的，主要用于在运行时将两个Method进行交换，我们可以将Method Swizzling代码写到任何地方，但是只有在这段Method Swilzzling代码执行完毕之后互换才起作用。而且Method Swizzling也是iOS中AOP(面相切面编程)的一种实现方式，我们可以利用苹果这一特性来实现AOP编程。
* 方法互换、页面统计、
* [iOS黑魔法－Method Swizzling](http://www.cocoachina.com/ios/20160121/15076.html)


### 9.如何实现动态添加方法和属性？ 

* 动态添加方法
    - 如果一个类方法非常多，加载类到内存的时候也比较耗费资源，需要给每个方法生成映射表，可以使用动态给某个类，添加方法解决。
    - 注解：OC 中我们很习惯的会用懒加载，当用到的时候才去加载它，但是实际上只要一个类实现了某个方法，就会被加载进内存。当我们不想加载这么多方法的时候，就会使用到 runtime 动态的添加方法。
* 动态添加属性
    - 原理：给一个类声明属性，其实本质就是给这个类添加关联，并不是直接把这个值的内存空间添加到类存空间。
    - 应用场景：给系统的类添加属性的时候,可以使用runtime动态添加属性方法。
    - 注解：系统 NSObject 添加一个分类，我们知道在分类中是不能够添加成员属性的，虽然我们用了@property，但是仅仅会自动生成get和set方法的声明，并没有带下划线的属性和方法实现生成。但是我们可以通过runtime就可以做到给它方法的实现。

### 10.说一下对 `isa` 指针的理解， 对象的`isa` 指针指向哪里？`isa` 指针有哪两种类型？（注意区分不同对象）

- sa指针是什么？
    * 我们经常使用id来声明一个对象，本质上，我们创建的一个对象或实例其实就是一个struct objc_object结构体，而我们常用的id也就是这个结构体的指针。这个结构体只有一个成员变量，这是一个Class类型的变量isa，也是一个结构体									指针。面向对象中每一个对象都必须依赖一个类来创建，因此对象的isa指针就指向对象所属的类根据这个类模板能够创建出实例变量、实例方法等。
- 对象的isa指针
    * 每个实例对象有个isa的指针,他指向对象的类
- 类对象的isa指针
    * Class里也有个isa的指针, 指向meteClass(元类)。
- 元类的isa指针
    * 元类保存了类方法的列表。当类方法被调用时，先会从本身查找类方法的实现，如果没有，元类会向他父类查找该方法。同时注意的是：元类（meteClass）也是类，它也是对象。元类也有isa指针,它的isa指针最终指向的是一个根元类(root meteClass).根元类的isa指针指向本身，这样形成了一个封闭的内循环。

![image](http://hi.csdn.net/attachment/201201/19/0_1326963670oeC1.gif)

### 11.`Obj-C` 中的类信息存放在哪里？ 

* OC的类本质就是结构体，通过封装一些映射方法，使你能更加方便地通过类和对象的方式来操作和使用这个结构体中的数据
* 这个结构体存放了类的"元数据"(metadata)

### 12.一个 `NSObject` 对象占用多少内存空间？

* Class 实际上是一个指向 objc_class 的结构体指针，也就是说 NSObject 最终声明为一个 指向结构体 objc_class 的名为 isa 的结构体指针。既然是指针，在32位系统中占 4个 字节，在64位系统中占 8 个字节。

### 13.说一下对 `class_rw_t` 的理解？
### 14.说一下对 `class_ro_t` 的理解？
### 15.说一下 `Runtime` 消息解析。



### 16.说一下 `Runtime` 消息转发。

* 通常情况下，在我们调用不属于某个对象的方法的时候，我们的应用就会崩溃crash，在崩溃之前编译器会进行消息转发机制，总共给了我们三次机会来避免这样的崩溃并尽可能的找到方法的响应者。

![image](https://upload-images.jianshu.io/upload_images/783864-d30b853ee14f829d.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

* 首先先看第一阶段。我们都知道，在iOS开发当中我们需要非常的注意用户体验。单纯的是因为数据类型错误而导致应用出现闪退，这样的处理会极大的影响使用app的用户。因此，我们可以通过class_addMethod这个函数来动态的添加这种错误的处理
* 在第二阶段最开始的时候，这时候已经默许了你并不想使用消息接收者来响应这个方法，所以我们需要找到消息接盘侠 —— 在iOS中不支持多继承，尽管我们可以通过协议和组合模式实现伪多继承。伪多继承和多继承的区别在于：多继承是将多个类的功能组合到一个对象当中，而伪多继承多个类的功能依旧分布在不同对象当中，但是对象彼此对消息发送者透明。那么，如果我们消息转发给另一个对象可以用来实现这种伪多继承。
* 如果你依旧没有为这个方法找到另外一个调用者，那么阻止你app闪退的最后时刻到来了。runtime需要生成一个methodSignature变量来组装，这将通过调用消息接收者的-(NSMethodSignature *)methodSignatureForSelector:获取，这个变量包含了方法的参数类型、参数个数以及消息接收者等信息。接着把这个变量组装成一个NSInvocation对象进行最后一次的消息转发，调用接收者的-forwardInvocation:来进行最后的挽救机会。这意味着我们可以尽情的对invocation做任何事情，包括随意修改参数值、消息接收者等。

总的来说整个消息发送的过程可以归纳成下面这张图：
![image](https://upload-images.jianshu.io/upload_images/783864-6307edd44a777c2c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

### 17.如何运用 `Runtime` 字典转模型？

* 结合kvc，Runtime 遍历 ivar_list。

### 18.如何运用 `Runtime` 进行模型的归解档？

* Runtime 遍历 ivar_list。
* 有众多属性的时候就用runtime归档解档。

### 19.在 `Obj-C` 中为什么叫发消息而不叫函数调用？
### 20.说一下对 `runtime` 的理解。（主要讲一下消息机制，是对上述的总结）

* Runtime又叫运行时，是一套底层C语言的API，其为iOS内部的核心之一，我们平时编写的OC代码底层都是基于它来实现的。比如：[target doSomething];底层运行时会被编译器转化成objc_msgSend(target,@selector(doSomething)); 带参数的[target doSomething:arg1...]; 会被底层运行时会被编译器转化成objc_msgSend(target, @selector(doSomething),arg1, arg2, ...);
* Objc 在三种层面上与 Runtime 系统进行交互：
    - 通过 Objective-C 源代码
    - 通过 Foundation 框架的 NSObject 类定义的方法
    - 通过对 Runtime 库函数的直接调用
* Runtime有5大作用：发送消息，交换方法，动态添加方法，给分类添加属性，字典转模型；
* 任何方法调用的本质就是发送一个消息，用runtime发送消息，OC底层就是通过runtime实现的。

### 21.说一下 `Runtime` 的方法缓存？存储的形式、数据结构以及查找的过程？


### 22.是否了解 `Type Encoding`? 


## 3.Runloop
### 1.`Runloop` 和线程的关系？ 

- 总的说来，Run loop，正如其名，loop表示某种循环，和run放在一起就表示一直在运行着的循环。实际上，run loop和线程是紧密相连的，可以这样说run loop是为了线程而生，没有线程，它就没有存在的必要。Run loops是线程的基础架构部分， Cocoa 和 CoreFundation 都提供了 run loop 对象方便配置和管理线程的 run loop （以下都以 Cocoa 为例）。每个线程，包括程序的主线程（ main thread ）都有与之相应的 run loop 对象。
- runloop 和线程的关系：
    * 主线程的run loop默认是启动的。
iOS的应用程序里面，程序启动后会有一个如下的main()函数

```
int main(int argc, char * argv[]) {
   @autoreleasepool {
       return UIApplicationMain(argc, argv, nil, NSStringFromClass([AppDelegate class]));
   }
}
```
重点是UIApplicationMain()函数，这个方法会为main thread设置一个NSRunLoop对象，这就解释了：为什么我们的应用可以在无人操作的时候休息，需要让它干活的时候又能立马响应。
    * 对其它线程来说，run loop默认是没有启动的，如果你需要更多的线程交互则可以手动配置和启动，如果线程只是去执行一个长时间的已确定的任务则不需要。
    * 在任何一个 Cocoa 程序的线程中，都可以通过以下代码来获取到当前线程的 run loop 。

```
NSRunLoop *runloop = [NSRunLoop currentRunLoop];
```
- 参考链接：[《Objective-C之run loop详解》](https://blog.csdn.net/wzzvictory/article/details/9237973)。

### 2.讲一下 `Runloop` 的 `Mode`?(越详细越好) 

- model主要是用来指定事件在运行循环中的优先级的，分为：
    * NSDefaultRunLoopMode（kCFRunLoopDefaultMode）：默认，空闲状态
    * UITrackingRunLoopMode：ScrollView滑动时
    * UIInitializationRunLoopMode：启动时
    * NSRunLoopCommonModes（kCFRunLoopCommonModes）：Mode集合
- 苹果公开提供的 Mode 有两个：
    * NSDefaultRunLoopMode（kCFRunLoopDefaultMode）
    * NSRunLoopCommonModes（kCFRunLoopCommonModes）

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
### 20.网络请求的状态码都大致代表什么意思？
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
### 补充：在实际使用Instruments 可监控插件，你会注意哪些有用的信息？
### 补充：使用哪个事件来检测用户轻按按钮？

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

* 对于atomic的属性，系统生成的 getter/setter 会保证 get、set 操作的完整性，不受其他线程影响。比如，线程 A 的 getter 方法运行到一半，线程 B 调用了 setter：那么线程 A 的 getter 还是能得到一个完好无损的对象。 而nonatomic就没有这个保证了。所以，nonatomic的速度要比atomic快。据说快大约20倍。
* 不过atomic可并不能保证线程安全。如果线程 A 调了 getter，与此同时线程 B 、线程 C 都调了 setter——那最后线程 A get 到的值，3种都有可能：可能是 B、C set 之前原始的值，也可能是 B set 的值，也可能是 C set 的值。同时，最终这个属性的值，可能是 B set 的值，也有可能是 C set 的值。
* 解决方案是加锁。

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
### 补充：简述Xcode7和Xcode8的异同
### 补充：描述iOS 10的一些新特性（包括系统和开发环境）



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
### 补充：7.作为开发苹果应用者有多长时间，拥有哪些苹果设备？
### 补充：8.平时你经常访问哪些技术类网址
### 补充：9.为什么选择iOS开发，你对它的前景和本身有什么想法？请简要回答。
### 补充：10.你有自己的开源项目吗，用什么托管的代码？
