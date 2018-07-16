# iOSInterviewQuestion
## 知乎上MrPeak大神的面试题（附答案）

- 04《iOS中级面试题》，面试题来源是MrPeak大神在知乎上发的帖子[《如何面试iOS 工程师》](https://www.zhihu.com/question/19604641)
- 如有纰漏，请向微博[@爱吃兔兔的胡萝卜吖](https://weibo.com/6447187962/)反馈。


# 索引

# 知乎上MrPeak大神的面试题

1. 什么是arc？（arc是为了解决什么问题诞生的？）
2. 请解释以下keywords的区别： assign vs weak, __block vs __weak
3. __block在arc和非arc下含义一样吗？
4. 使用nonatomic一定是线程安全的吗？（）
5. 描述一个你遇到过的retain cycle例子。
6. +(void)load; +(void)initialize；有什么用处？
7. 为什么其他语言里叫函数调用， objective c里则是给对象发消息（或者谈下对runtime的理解）
8. 什么是method swizzling?
9. UIView和CALayer是啥关系？
10. 如何高性能的给UIImageView加个圆角？（不准说layer.cornerRadius!）
11. 使用drawRect有什么影响？（这个可深可浅，你至少得用过。。）
12. ASIHttpRequest或者SDWebImage里面给UIImageView加载图片的逻辑是什么样的？
13. 麻烦你设计个简单的图片内存缓存器（移除策略是一定要说的）
14. 讲讲你用Instrument优化动画性能的经历吧（别问我什么是Instrument）
15. loadView是干嘛用的？
16. viewWillLayoutSubView你总是知道的。
17. GCD里面有哪几种Queue？你自己建立过串行queue吗？背后的线程模型是什么样的？
18. 用过coredata或者sqlite吗？读写是分线程的吗？遇到过死锁没？咋解决的？
19. http的post和get啥区别？（区别挺多的，麻烦多说点）
20. 我知道你大学毕业过后就没接触过算法数据结构了，但是请你一定告诉我什么是Binary search tree? search的时间复杂度是多少？

## 一份“有点难”的面试题
1. NSString如何计算字符的个数？
2. PKI体系当中加密和签名有什么区别？
3. 如何自己高效实现NSUserDefault?
4. 解释下tcp的慢启动特性。
5. 如何用HTTP实现长连接？
6. HTTP2.0针对同一个域名的多个请求，会建立多少个tcp连接？
7. 数据库建表的时候索引有什么用？
8. Full Text Search为什么快？
9. iOS下如何实现指定线程数目的线程池？
10. 介绍下iOS设备获取唯一设备号的历史变迁。
11. 函数式编程当中的 first-class function是什么意思呢？
12. 如何使用runtime hook一个class的某个方法，又如何hook某个instance的方法？
13. 谈下Objective C都有哪些锁机制，你一般用哪个？
14. 聊下HTTP post的body体使用form-urlencoded和multipart/form-data的区别。
15. 让你设计一种机制检测UIViewController的内存泄漏，你会怎么做？
16. 通过[UIImage imageNamed:]生成的对象什么时候被释放？
17. applicationWillEnterForeground和applicationDidBecomeActive都会在哪些场景下被调用？举例越多越好。
18. 如何终止正在运行的工作线程？
19. 穷举iOS下所有的本地持久化方案。
20. 如果公司强制996，你有什么心里话要对老板说吗？

## 补充一份基础的面试题
1. 在oc中如何实现深度拷贝
2. 请描述什么是delegate、block、NSNotification，他们有什么作用
3. 请写出一个线程安全的单例模式
4. 解释属性中strong、weak、assign、copy的区别
5. #import和#include的区别
6. 描述tableView的重用机制
7. Object-C有多继承吗？没有的话用什么代替？
8. category与继承之间的区别
9. #define和const定义的变量，有什么区别
10. TCP和UDP的区别是什么？
11. MD5和Base64的区别是什么，各自场景是什么？
12. 二叉搜索树的概念，时间复杂度多少？
13. 如何添加一个自定义字体到工程中
14. 如何制作一个静态库/动态库，他们的区别是什么？
15. Configuration中，debug和release的区别是什么？
16. push view controller 和 present view controller的区别
17. 描述下tableview cell的重用机制
18. UIView的frame和bounds的区别是什么
19. new与alloc init的区别
20. NSArray实例化时，array与init的区别
21. 哪些类不适合使用单例模式？即使他们在周期中只会出现一次。
22. Notification的使用场景是什么？同步还是异步？
23. 简单介绍一下KVC和KVO，他们都可以应用在哪些场景？
24. UIButton的父类是什么？UILabel呢？
25. 发送10个网络请求，然后再接收到所有回应之后执行后续操作，如何实现？
26. 实现一个第三方控件，可以在任何时候出现在APP界面最上层
27. 不同版本的APP，数据库结构变化了，如何处理?
28. 内存中的栈和堆的区别是什么？那些数据在栈上，哪些在堆上？
29. block中的weak self，是任何时候都需要加的么？
30. GCD的queue，main queue中执行的代码，一定是在main thread么？
31. NSOperationQueue有哪些使用方式
32. NSThread中的Runloop的作用，如何使用？
33. .h文件中的变量，外部可以直接访问么？（注意是变量，不是property）
34. 讲述一下runtime的概念，message send如果寻找不到相应的对象，会如何进行后续处理 ？
35. 利用runtime实现一个对象的拷贝



# 补充一份面试经验题
1. 说一下OC的反射机制；
2. block的实质是什么？有几种block？分别是怎样产生的？
3. __block修饰的变量为什么能在block里面能改变其值？
4. 说一下线程之间的通信。
5. 你们应用的崩溃率是多少？
6. 说一下hash算法。
7. NSDictionary的实现原理是什么？
8. 你们的App是如何处理本地数据安全的（比如用户名的密码）？
9. 遇到过BAD_ACCESS的错误吗？你是怎样调试的？
10. 什么是指针常量和常量指针？
11. 不借用第三个变量，如何交换两个变量的值？要求手动写出交换过程。
12. 若你去设计一个通知中心，你会怎样设计？
13. 如何去设计一个方案去应对后端频繁更改的字段接口？
14. KVO、KVC的实现原理
15. 用递归算法求1到n的和
16. category为什么不能添加属性？
17. 说一下runloop和线程的关系。
18. 说一下autoreleasePool的实现原理。
19. 说一下简单工厂模式，工厂模式以及抽象工厂模式？
20. 如何设计一个网络请求库？
21. 说一下多线程，你平常是怎么用的？
22. 说一下UITableViewCell的卡顿你是怎么优化的？
23. 看过哪些三方库？说一下实现原理以及好在哪里？
24. 说一下HTTP协议以及经常使用的code码的含义。
25. 设计一套缓存策略。
26. 设计一个检测主线和卡顿的方案。
27. 说一下runtime，工作是如何使用的？看过runtime源码吗？
28. 说几个你在工作中使用到的线程安全的例子。
29. 用过哪些锁？哪些锁的性能比较高？
30. 说一下HTTP和HTTPs的请求过程？
31. 说一下TCP和UDP
32. 说一下静态库和动态库之间的区别
33. load和initialize方法分别在什么时候调用的？
34. NSNotificationCenter是在哪个线程发送的通知？
35. 用过swift吗？如果没有，平常有学习吗？
36. 说一下你对架构的理解？
37. 为什么一定要在主线程里面更新UI？

# 知乎上面试题
1. 讲述一次在这个APP中，用户触发了一个事件，引起了一个服务请求，然后获取服务端返回，并且更新前端界面的过程。请说的详细一点，比如数据经过了哪些类的处理，每一次传递时的格式是怎么样的？
2. 你参与的APP，是如何处理多个服务的同步发起的？随后让面试者说一下APP的界面架构，这个比较随意。问完了项目，就开始基础知识题啦~
### Model层：
3. 数据持久化存储方案有哪些？
4. 沙盒的目录结构是怎样的？各自一般用于什么场合？
5. SQL语句问题：inner join、left join、right join的区别是什么？
6. sqlite的优化网络通信用过哪些方式（100%的人说了AFNetworking...）
7. 如何处理多个网络请求并发的情况
8. 在网络请求中如何提高性能
9. 在网络请求中如何保证安全性 

## 语言与基础知识：
1. 内存中的栈和堆的区别是什么？
2. 那些数据在栈上，哪些在堆上？
3. #define和const定义的变量，有什么区别
4. 什么情况下会出现内存的循环引用block中的weak 
5. self，是任何时候都需要加的么？
6. GCD的queue，main queue中执行的代码，一定是在main thread么？
7. NSOperationQueue有哪些使用方式
8. NSThread中的Runloop的作用，如何使用？
9. .h文件中的变量，外部可以直接访问么？（注意是变量，不是property）
10. 讲述一下runtime的概念，
11. message send如果寻找不到相应的对象，会如何进行后续处理 ？
12. TCP和UDP的区别是什么？
13. MD5和Base64的区别是什么，各自场景是什么？
14. 二叉搜索树的概念，时间复杂度多少？架构：（我们招的不是架构师，这方面问的不多，而且从之前对APP的架构介绍里可以边听边问）哪些类不适合使用单例模式？即使他们在周期中只会出现一次。
15. Notification的使用场景是什么？同步还是异步？
16. 简单介绍一下KVC和KVO，他们都可以应用在哪些场景？ 

## APP相关：
1. 如何添加一个自定义字体到工程中
2. 如何制作一个静态库/动态库，他们的区别是什么？
3. Configuration中，debug和release的区别是什么？
4. 简单介绍下发送系统消息的机制（APNS） UI：
系统如何寻找到需要响应用户操作的那个Responder
5. 多屏幕尺寸的适配
6. UIButton的父类是什么？UILabel呢？
7. push view controller 和 present view controller的区别
8. 描述下tableview cell的重用机制
9. UIView的frame和bounds的区别是什么 
10. 发送10个网络请求，然后再接收到所有回应之后执行后续操作，如何实现？
11. 实现一个第三方控件，可以在任何时候出现在APP界面最上层
12. 实现一个最简单的点击拖拽功能。上面那个拖拽之外，如果在手放开时，需要根据速度往前滑动呢？
13. 如何减小一个应用程序的尺寸？
14. 如何提高一个性用程序的性能？
15. 不同版本的APP，数据库结构变化了，如何处理?


# 知乎上MrPeak大神的面试题

### 1. 什么是arc？（arc是为了解决什么问题诞生的？）

> 现在有不少程序员是直接从arc上手的，从没接触过mrc，对arc的理解仅仅停留在apple帮助管理内存的层面。这个问题真正想了解的是对内存管理的理解，retain release虽然不用写了，但arc下还是会有内存泄漏野指针crash的bug存在。如果能从retain count这种内存管理策略的角度去阐述arc诞生的意义就算答对了。如果还能扯下其他类型的策略，比如java里的mark and sweep，那就加分点赞。

* ARC: automatic reference counting自动引用计数。
* 在对象被创建时 retain count +1，在对象被release时 retain count -1.当retain count 为0 时，销毁对象。 
程序中加入autoreleasepool的对象会由系统自动加上autorelease方法，如果该对象引用计数为0，则销毁。
* 使用ARC以后，不论是strong还是weak类型的指针，都不再会指向一个dealloced的对象，从根源上解决了意外释放导致的crash。

那么ARC是为了解决什么问题诞生的呢？这个得追溯到MRC手动内存管理时代说起。
* MRC下内存管理的缺点：
    - 当我们要释放一个堆内存时，首先要确定指向这个堆空间的指针都被release了。（避免提前释放）
    - 释放指针指向的堆空间，首先要确定哪些指针指向同一个堆，这些指针只能释放一次。（MRC下即谁创建，谁释放，避免重复释放） 
    - 模块化操作时，对象可能被多个模块创建和使用，不能确定最后由谁去释放。
    - 多线程操作时，不确定哪个线程最后使用完毕
#### 补充：java里面的垃圾自动回收机制
* 最基本的垃圾收集算法有四种
    - 标记-清除算法(mark-sweep)
        - 顾名思义，标记-清除算法分为两个阶段，标记(mark)和清除(sweep). 
        - 在标记阶段，collector从mutator根对象开始进行遍历，对从mutator根对象可以访问到的对象都打上一个标识，一般是在对象的header中，将其记录为可达对象。
        - 而在清除阶段，collector对堆内存(heap memory)从头到尾进行线性的遍历，如果发现某个对象没有标记为可达对象-通过读取对象的header信息，则就将其回收。
        - 标记-清除算法的比较大的缺点就是垃圾收集后有可能会造成大量的内存碎片，会导致Mutator一直处于暂停状态，而Collector一直在尝试进行垃圾收集，直到Out of Memory。
    - 标记-压缩算法(mark-compact)
    - 复制算法(copying)
    - 引用计数算法(reference counting)
* 首先是mutator和collector，这两个名词经常在垃圾收集算法中出现，collector指的就是垃圾收集器，而mutator是指除了垃圾收集器之外的部分，比如说我们应用程序本身。mutator的职责一般是NEW(分配内存),READ(从内存中读取内容),WRITE(将内容写入内存)，而collector则就是回收不再使用的内存来供mutator进行NEW操作的使用。

### 2. 请解释以下keywords的区别： assign vs weak, __block vs __weak

> 这道题属于基础语法题，可以网上搜到答案。不过真有不少同学不知道weak在对象释放后会置为nil。__block关键字的理解稍微难点，因为在arc和mrc下含义（对retain count的影响）完全不同。理解了这几个关键字就能应付使用block时引入retain cycle的风险了。这题还在内存管理的范畴之内。

* assign适用于基本数据类型，weak是适用于NSObject对象，并且是一个弱引用。 
    - assign其实也可以用来修饰对象，那么我们为什么不用它呢？因为被assign修饰的对象在释放之后，指针的地址还是存在的，也就是说指针并没有被置为nil。如果在后续的内存分配中，刚好分到了这块地址，程序就会崩溃掉。 
    - 而weak修饰的对象在释放之后，指针地址会被置为nil。所以现在一般弱引用就是用weak。 
* 首先__block是用来修饰一个变量，这个变量就可以在block中被修改（参考block实现原理） 
* __block：使用__block修饰的变量在block代码快中会被retain（ARC下，MRC下不会retain） 
* __weak：使用__weak修饰的变量不会在block代码块中被retain 
* 同时，在ARC下，要避免block出现循环引用 __weak typedof(self)weakSelf = self;

### 3. __block在arc和非arc下含义一样吗？

* 一般在block中修改变量都需要事先加__block进行修饰。
* 在非arc中，__block修饰的变量的引用计算是不变的。
* 在arc中，会引用到，并且计算+1；
* 非arc下可使用（arc直接使用__weak即可）

```
//非ARC
__block typeof(self) weakSelf = self;
self.myBlock = ^(int paramInt){ 
//使用weakSelf访问self成员
 [weakSelf anotherFunc];
};
```
这样可以解决循环引用问题。

### 4. 使用nonatomic一定是线程安全的吗？（）

> 看这题的问法不用想答案肯定是NO。有些人说不出所以然，有些人知道通过property的方式使用才能保证安全，还有人知道这个用来做多线程安全会有性能损耗，更有出色的候选人能谈atomic,synchronized,NSLock,pthread mutex,OSSpinLock的差别。

* 不是
* atomic 和 nonatomic 的区别在于，系统自动生成的 getter/setter 方法不一样。其实质就是，atomic比nonatomic多了一个互斥加锁代码，避免该变量的读写不同步问题。具体使用 @synchronized(self){//code } 
* 不安全的情况例如：一个线程在连续多次读取某属性值的过程中有别的线程在同时改写该值，那么即便将属性声明为 atomic，也还是会读到不同的属性值。因此，开发iOS程序时一般都会使用 nonatomic 属性。但是在开发 Mac OS X 程序时，使用 atomic 属性通常都不会有性能瓶颈。




### 5. 描述一个你遇到过的retain cycle例子。

> 说没遇到过的我很难相信你有过成熟项目的经历。这题答不出了会扣很多很多分。用过block，写过delegate的肯定都踩过坑。

block中的循环引用：一个viewController

```
@property (nonatomic,strong)HttpRequestHandler * handler;
    @property (nonatomic,strong)NSData          *data;
    _handler = [httpRequestHandler sharedManager];
    [ downloadData:^(id responseData){
        _data = responseData;
    }];
```
self 拥有_handler, _handler 拥有block, 
block拥有self（因为使用了self的_data属性，block会copy 一份self） 

解决方法：


```
__weak typedof(self)weakSelf = self
    [ downloadData:^(id responseData){
        weakSelf.data = responseData;
    }];
```

* 常出现循环引用的三种场景：
    - 计时器NSTimer
        - NSTimer经常会被作为某个类的成员变量，而NSTimer初始化时要指定self为target，容易造成循环引用。
    - block
        - block在copy时都会对block内部用到的对象进行强引用(ARC)或者retainCount增1(非ARC)。在ARC与非ARC环境下对block使用不当都会引起循环引用问题，一般表现为，某个类将block作为自己的属性变量，然后该类在block的方法体里面又使用了该类本身
    - 委托delegate
        - 声明delegate时请用assign(MRC)或者weak(ARC)


### 6. +(void)load; +(void)initialize；有什么用处？

> 这题属于runtime范畴，我遇到过能说出对runtime的理解却不知道这两个方法的候选人。所以答不出来也没关系，这属于细节知识点，是加分项，能答出两个message各在什么阶段接收就可以了。

* + initialize 和 + load 是 NSObject 类的两个类方法，它们会在运行时自动调用，我们可以利用其特性做一些初始化操作。
* initialize和load的区别在于：load是只要类所在文件被引用就会被调用，而initialize是在类或者其子类的第一个方法被调用前调用。所以如果类没有被引用进项目，就不会有load调用；但即使类文件被引用进来，但是没有使用，那么initialize也不会被调用。
* initialize
    - + (void)initialize 消息是在该类接收到其第一个消息之前调用。
    - 关于这里的第一个消息需要特别说明一下，对于 NSObject 的 runtime 机制而言，其在调用 NSObject 的 + (void)load 消息不被视为第一个消息，但是，如果像普通函数调用一样直接调用 NSObject 的 + (void)load 消息，则会引起 + (void)initialize 的调用。反之，如果没有向 NSObject 发送第一个消息，+ (void)initialize 则不会被自动调用。
    - 在应用程序的生命周期中，runtime 只会向每个类发送一次 + (void)initialize 消息.
    - 如果该类是子类，且该子类中没有实现 + (void)initialize 消息，或者子类显示调用父类实现 [super initialize], 那么则会调用其父类的实现。也就是说，父类的 + (void)initialize 可能会被调用多次。
    - 如果类包含分类（扩展 catagory），且分类重写了initialize方法，那么则会调用分类的 initialize 实现，而原类的该方法实现不会被调用。
    - 这个机制同 NSObject 的其他方法(除 + (void)load 方法) 一样，即如果原类同该类的分类包含有相同的方法实现，那么原类的该方法被隐藏而无法被调用。
    - 父类的 initialize 方法先于子类的 initialize 方法调用。
* load
    - + (void)load 会在类或者类的分类添加到 Objective-c runtime 时调用，该调用发生在 application:willFinishLaunchingWithOptions: 调用之前调用。
    - 父类的 +load 方法先于子类的 +load 方法调用，分类的 +load 方法先于类本身的 +load 方法调用。
    - Runtime调用+(void)load时没有autorelease pool:
        - 原因是runtime调用+(void)load的时候，程序还没有建立其autorelease pool，所以那些会需要使用到autorelease pool的代码，都会出现异常。这一点是非常需要注意的，也就是说放在+(void)load中的对象都应该是alloc出来并且不能使用autorelease来释放。
    - 不需要显示使用super调用父类中的方法
        - super的方法会成功调用，但是这是多余的，因为runtime对自动对父类的+(void)load方法进行调用，而+(void)initialize则会随子类自动激发父类的方法（如Apple文档中所言）不需要显示调用。
* 总结
    - +(void)load
        - 执行时机    在程序运行后立即执行
        - 若自身未定义，是否沿用父类的方法？   否
        - 类别中的定义  全都执行，但后于类中的方法
    - +(void)initialize
        - 执行时机    在类的方法第一次被调时执行
        - 若自身未定义，是否沿用父类的方法？   是
        - 类别中的定义  覆盖类中的方法，只执行一个

### 7. 为什么其他语言里叫函数调用， objective c里则是给对象发消息（或者谈下对runtime的理解）

> 这题考查的是objective c这门语言的dynamic特性，需要对比c++这类传统静态方法调用才能理解。最好能说出一个对象收到message之后的完整的流程是如何的。对runtime有完整理解的候选人还能说出oc的对象模型。

* 先来看看怎么理解发送消息的含义：
    - [receiver message]会被编译器转化为： 
        - objc_msgSend(receiver, selector) 
    - 如果消息含有参数，则为： 
        - objc_msgSend(receiver, selector, arg1, arg2, ...)
    - 如果消息的接收者能够找到对应的selector，那么就相当于直接执行了接收者这个对象的特定方法；否则，消息要么被转发，或是临时向接收者动态添加这个selector对应的实现内容，要么就干脆玩完崩溃掉。
    - 现在可以看出[receiver message]真的不是一个简简单单的方法调用。因为这只是在编译阶段确定了要向接收者发送message这条消息，而receive将要如何响应这条消息，那就要看运行时发生的情况来决定了。
    - Objective-C 的 Runtime 铸就了它动态语言的特性，这些深层次的知识虽然平时写代码用的少一些，但是却是每个 Objc 程序员需要了解的。
    - Objc Runtime使得C具有了面向对象能力，在程序运行时创建，检查，修改类、对象和它们的方法。可以使用runtime的一系列方法实现。
* 向object发送消息时，Runtime库会根据object的isa指针找到这个实例object所属于的类，然后在类的方法列表以及父类方法列表寻找对应的方法运行。id是一个objc_object结构类型的指针，这个类型的对象能够转换成任何一种对象。
* 然后再来看看消息发送的函数：objc_msgSend函数
* 在引言中已经对objc_msgSend进行了一点介绍，看起来像是objc_msgSend返回了数据，其实objc_msgSend从不返回数据而是你的方法被调用后返回了数据。下面详细叙述下消息发送步骤：
* 检测这个 selector 是不是要忽略的。比如 Mac OS X 开发，有了垃圾回收就不理会 retain,release 这些函数了。 
* 检测这个 target 是不是 nil 对象。ObjC 的特性是允许对一个 nil  对象执行任何一个方法不会 Crash，因为会被忽略掉。 
* 如果上面两个都过了，那就开始查找这个类的 IMP，先从 cache 里面找，完了找得到就跳到对应的函数去执行。 
* 如果 cache 找不到就找一下方法分发表。 
* 如果分发表找不到就到超类的分发表去找，一直找，直到找到NSObject类为止。 
* 如果还找不到就要开始进入动态方法解析了，消息转发。

后面还有： 

    动态方法解析resolveThisMethodDynamically 

    消息转发forwardingTargetForSelector


### 8. 什么是method swizzling?

> 说了解runtime但没听过method swizzling是骗人的。这题很容易搜到答案。定位一些疑难杂症bug，hack老项目实现，阅读第三方源码都有机会接触到这个概念。

* Method Swizzling 原理（方法搅拌？）
* 在Objective-C中调用一个方法，其实是向一个对象发送消息，查找消息的唯一依据是selector的名字。利用Objective-C的动态特性，可以实现在运行时偷换selector对应的方法实现，达到给方法挂钩的目的。 
* 每个类都有一个方法列表，存放着selector的名字和方法实现的映射关系。IMP有点类似函数指针，指向具体的Method实现。

![image](https://upload-images.jianshu.io/upload_images/1771779-da34056b24fef205.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/509)


    - 我们可以利用 method_exchangeImplementations 来交换2个方法中的IMP，
    - 我们可以利用 class_replaceMethod 来修改类，
    - 我们可以利用 method_setImplementation 来直接设置某个方法的IMP， 
    - 。。。。
* 归根结底，都是偷换了selector的IMP，如下图所示：

![image](https://upload-images.jianshu.io/upload_images/595396-33c99f32ffc5fdda.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/483)

* 具体的做法，
    - 首先，用Categroy建立自己的方法。
    - 在+load方法中去实现方法交换的代码（load可以保证被调用，其他方法都不靠谱）

```
Method ori_Method =  class_getInstanceMethod([MYclass class], @selector(lastObject));  
Method my_Method = class_getInstanceMethod([MYclass class], @selector(myLastObject));  
method_exchangeImplementations(ori_Method, my_Method);
```


[参考文献](https://blog.csdn.net/yiyaaixuexi/article/details/9374411)

### 9. UIView和CALayer是啥关系？

> 能答出UIView是CALayer的delegate就及格了，能说出UIView主要处理事件，CALayer负责绘制就更好，再聊下二者在使用过程中对动画流畅性影响的注意点就superb。UI流畅性是个大话题，推荐看下这两篇文章。[中餐](https://blog.ibireme.com/2015/11/12/smooth_user_interfaces_for_ios/)，西餐。

* UIView是iOS系统中界面元素的基础，所有的界面元素都继承自它。它本身完全是由CoreAnimation来实现的 （Mac下似乎不是这样）。它真正的绘图部分，是由一个叫CALayer（Core Animation Layer）的类来管理。 UIView本身，更像是一个CALayer的管理器，访问它的跟绘图和跟坐标有关的属性，例如frame，bounds等 等，实际上内部都是在访问它所包含的CALayer的相关属性。
* UIView有个layer属性，可以返回它的主CALayer实例，UIView有一个layerClass方法，返回主layer所使用的 类，UIView的子类，可以通过重载这个方法，来让UIView使用不同的CALayer来显示，例如通过

```
- (class) layerClass {

         return ([CAEAGLLayer class]);
    }
    
```

使某个UIView的子类使用GL来进行绘制。

* UIView的CALayer类似UIView的子View树形结构，也可以向它的layer上添加子layer，来完成某些特殊的表 示。例如下面的代码

```
grayCover = [[CALayer alloc] init];

    grayCover.backgroundColor = [[[UIColor blackColor] colorWithAlphaComponent:0.2] CGColor];

    [self.layer addSubLayer: grayCover];
```

会在目标View上敷上一层黑色的透明薄膜。

* UIView的layer树形在系统内部，被系统维护着三份copy（这段理解有点吃不准）。
    - 逻辑树，就是代码里可以操纵的，例如更改layer的属性等等就在这一份。
    - 动画树，这是一个中间层，系统正在这一层上更改属性，进行各种渲染操作。
    - 显示树，这棵树的内容是当前正被显示在屏幕上的内容。

这三棵树的逻辑结构都是一样的，区别只有各自的属性。


### 10. 如何高性能的给UIImageView加个圆角？（不准说layer.cornerRadius!）

> 这题讨论的最多，还有说美工切图就搞定的。答主在项目里做过圆角头像的处理，里面的坑还真不少。cornerRadius会导致offscreen drawing有性能问题，美工切图无法适用有背景图的场景，即使加上shouldRasterize也有cache实效问题。正确的做法是切换到工作线程利用CoreGraphic API生成一个offscreen UIImage，再切换到main thread赋值给UIImageView。这里还涉及到UIImageView复用，圆角头像cache缓存（不能每次都去绘制），新旧头像替换等等逻辑。还有其他的实现方式，但思路离不开工作线程与主线程切换。

* 一般情况下给 UIImageView 或者说 UIKit 的控件添加圆角都是改变 clipsToBounds和 layer.cornerRadius, 这样大约两行代码就可以解决这个问题. 但是, 这样使用这样的方法会强制Core Animation 提前渲染屏幕的离屏绘制, 而离屏绘制就会为性能带来负面影响.
* 使用Quartz2D直接绘制图片
    - 步骤： 
        - 创建目标大小(cropWidth，cropHeight)的画布。
        - 使用UIImage的drawInRect方法进行绘制的时候，指定rect为(-x，-y，width，height)。
        - 从画布中得到裁剪后的图像。

```
- (UIImage *)circleImage{ 
// NO 代表透明 
UIGraphicsBeginImageContextWithOptions(self.size, NO,0.0); 
// 获得上下文
CGContextRef ctx = UIGraphicsGetCurrentContext(); 
// 添加一个圆 
CGRect rect = CGRectMake(0, 0, self.size.width,self.size.height); 
// 裁剪CGContextClip(ctx);
CGContextAddEllipseInRect(ctx, rect); 
// 将图片画上去
[self drawInRect:rect]; 
UIImage *image =UIGraphicsGetImageFromCurrentImageContext(); 
// 关闭上下文
UIGraphicsEndImageContext(); 
return image;
} 
```

* 我们也可以使用另一种比较复杂的方式来为图片添加圆角, 这里就用到了贝塞尔曲线.

```
UIImageView *imageView = [[UIImageView alloc] initWithFrame:CGRectMake(0, 0, 100, 100)]; 
imageView.center = CGPointMake(200, 300); 
UIImage *anotherImage = [UIImage imageNamed:@"image"]; 
UIGraphicsBeginImageContextWithOptions(imageView.bounds.size, NO, 1.0); 
[[UIBezierPath bezierPathWithRoundedRect:imageView.bounds
                      cornerRadius:50] addClip];
[anotherImage drawInRect:imageView.bounds];
imageView.image = UIGraphicsGetImageFromCurrentImageContext(); 
UIGraphicsEndImageContext(); 
[self.view addSubview:imageView];

```


### 11. 使用drawRect有什么影响？（这个可深可浅，你至少得用过。。）

> 不少同学都用过drawRect或者看别人用过，但不知道这个api存在的含义。这不仅仅是另一种做UI的方式。drawRect会利用CPU生成offscreen bitmap，从而减轻GPU的绘制压力，用这种方式最UI可以将动画流畅性优化到极致，但缺点是绘制api复杂，offscreen cache增加内存开销。UI动画流畅性的优化主要平衡CPU和GPU的工作压力。推荐一篇文章：[西餐](https://note.youdao.com/)

* 用来画图，这个方法会在intiWithRect时候调用。
* drawRect方法依赖Core Graphics框架来进行自定义的绘制，但这种方法主要的缺点就是它处理touch事件的方式：每次按钮被点击后，都会用setNeddsDisplay进行强制重绘；而且不止一次，每次单点事件触发两次执行。这样这个方法的影响在于有touch event的时候之后，会重新绘制，很多这样的按钮的话就会比较影响效率。
* 以下都会被调用
    - 如果在UIView初始化时没有设置rect大小，将直接导致drawRect不被自动调用。drawRect 掉用是在Controller->loadView, Controller->viewDidLoad 两方法之后掉用的.所以不用担心在 控制器中,这些View的drawRect就开始画了.这样可以在控制器中设置一些值给View(如果这些View draw的时候需要用到某些变量 值).
    - 该方法在调用sizeToFit后被调用，所以可以先调用sizeToFit计算出size。然后系统自动调用drawRect:方法。
    - 通过设置contentMode属性值为UIViewContentModeRedraw。那么将在每次设置或更改frame的时候自动调用drawRect:。
    - 直接调用setNeedsDisplay，或者setNeedsDisplayInRect:触发drawRect:，但是有个前提条件是rect不能为0。


### 12. ASIHttpRequest或者SDWebImage里面给UIImageView加载图片的逻辑是什么样的？

> 很多同学没有读源码的习惯，别人的轮子拿来只是用用却不知道真正的营养都在源代码里面。这两个经典的framework代码并不复杂，很值得一读。能对一个UIImageView怎么通过url展示一张图片有完整的理解。涉及到的知识点也非常多，UITableViewCell的复用，memory cache, disk cache, 多线程切换，甚至http协议本身都需要有一定的涉及。

* 具体步骤
    - 第一步，下载SDWebImage，导入工程。
    - 第二步，在需要的地方导入头文件
        - #import "UIImageView+WebCache.h
    - 第三步，调用sd_setImageWithURL：方法缓存图片
* SDWebImage内部实现过程
    - 入口 setImageWithURL:placeholderImage:options: 会先把 placeholderImage 显示，然后 SDWebImageManager 根据 URL 开始处理图片。
    - 进入 SDWebImageManager-downloadWithURL:delegate:options:userInfo:，交给 SDImageCache 从缓存查找图片是否已经下载 queryDiskCacheForKey:delegate:userInfo:.
    - 先从内存图片缓存查找是否有图片，如果内存中已经有图片缓存，SDImageCacheDelegate 回调 imageCache:didFindImage:forKey:userInfo: 到 SDWebImageManager。
    - SDWebImageManagerDelegate 回调 webImageManager:didFinishWithImage: 到 UIImageView+WebCache 等前端展示图片。
    - 如果内存缓存中没有，生成 NSInvocationOperation 添加到队列开始从硬盘查找图片是否已经缓存。
    - 根据 URLKey 在硬盘缓存目录下尝试读取图片文件。这一步是在 NSOperation 进行的操作，所以回主线程进行结果回调 notifyDelegate:。
    - 如果上一操作从硬盘读取到了图片，将图片添加到内存缓存中（如果空闲内存过小，会先清空内存缓存）。SDImageCacheDelegate 回调 imageCache:didFindImage:forKey:userInfo:。进而回调展示图片。
    - 如果从硬盘缓存目录读取不到图片，说明所有缓存都不存在该图片，需要下载图片，回调 imageCache:didNotFindImageForKey:userInfo:。
    - 共享或重新生成一个下载器 SDWebImageDownloader 开始下载图片。
    - 图片下载由 NSURLConnection 来做，实现相关 delegate 来判断图片下载中、下载完成和下载失败。
    - connection:didReceiveData: 中利用 ImageIO 做了按图片下载进度加载效果。
    - connectionDidFinishLoading: 数据下载完成后交给 SDWebImageDecoder 做图片解码处理。
    - 图片解码处理在一个 NSOperationQueue 完成，不会拖慢主线程 UI。如果有需要对下载的图片进行二次处理，最好也在这里完成，效率会好很多。
    - 在主线程 notifyDelegateOnMainThreadWithInfo: 宣告解码完成，imageDecoder:didFinishDecodingImage:userInfo: 回调给 SDWebImageDownloader。
    - imageDownloader:didFinishWithImage: 回调给 SDWebImageManager 告知图片下载完成。
    - 通知所有的 downloadDelegates 下载完成，回调给需要的地方展示图片。
    - 将图片保存到 SDImageCache 中，内存缓存和硬盘缓存同时保存。写文件到硬盘也在以单独 NSInvocationOperation 完成，避免拖慢主线程。
    - SDImageCache 在初始化的时候会注册一些消息通知，在内存警告或退到后台的时候清理内存图片缓存，应用结束的时候清理过期图片。
    - SDWI 也提供了 UIButton+WebCache 和 MKAnnotationView+WebCache，方便使用。
    - SDWebImagePrefetcher 可以预先下载图片，方便后续使用。
* 总结：
    - SDWebImage封装了一切，你所需要的只是简单的set一个URL；
        - 设置一个展位图（可选择）；
        - 根据URL去内存中找，找到返回图片
        - 内存找不到，硬盘找，找到返回图片，内存做备份
        - 硬盘还找不到，去下载，返回图片，并进行存储（硬盘，内存）。
    - 其中有几点技术细节比较重要，
        - 图片在内存中是key-value的方式。
        - 在硬盘中是data的方式，imageWithData方法获取。
        - key-value方式是url的MD5。
        - 注册内存和硬盘通知，如果很吃紧，就删除部分。

### 13. 麻烦你设计个简单的图片内存缓存器（移除策略是一定要说的）

> 内存缓存是个通用话题，每个平台都会涉及到。cache算法会影响到整个app的表现。候选人最好能谈下自己都了解哪些cache策略及各自的特点。常见的有FIFO,LRU,LRU-2,2Q等等。由于NSCache的缓存策略不透明，一些app开发者会选择自己做一套cache机制，其实并不难。

* 写一个FIFO的存储机制，设置一定量的内存大小。每次添加新的图片后检查是否超出容量，如果超出则释放队列最前面的图片。

[关于缓存淘汰算法参考1](http://www.cnblogs.com/junyuhuang/p/5805168.html)
[关于缓存淘汰算法参考2](http://www.cnblogs.com/junyuhuang/p/5993612.html)

* 总结
    - FIFO
        - 工作原理：该算法是最简单的缓存淘汰算法，其原理正如它名字一样，最近使用过的对象放到缓存队列的末尾，队列头部保存的是最早使用的对象。
    - LRU
        - 算法思想：LRU算法的核心思想是基于“如果数据最近被访问过，它在未来也极有可能访问过”。因此如果数据的变化趋势符合这个思想，效果会比较好。
        - 工作原理：
            - 数据结构：链表，用于保存需要缓存的数据；HashMap，用来读取缓存中的数据，保证时间复杂读为O(1)
            - 实现：
                - 当数据读取时，有两种情况：
                    - 数据在缓存中，则把该数据从新移到链表头部
                    - 数据不在缓存中，则把数据插入到链表中。
                - 如何插入：
                    - 如果链表不满，则把数据插入链表头部
                    - 如果链表满了，则把尾部的数据删除，同时把其插入链表头 
    - LRU-k
        - 算法思想：
            - LRU-K中的K代表最近使用的次数，因此LRU可以认为是LRU-1。LRU-K的主要目的是为了解决LRU算法“缓存污染”的问题，其核心思想是将“最近使用过1次”的判断标准扩展为“最近使用过K次”
        - 工作原理：
            - 相比LRU，LRU-K需要多维护一个队列，用于记录所有缓存数据被访问的历史。只有当数据的访问次数达到K次的时候，才将数据放入缓存。当需要淘汰数据时，LRU-K会淘汰第K次访问时间距当前时间最大的数据。详细实现如下
            ![image](https://images2015.cnblogs.com/blog/472792/201611/472792-20161120232440279-600049881.png)
                - 数据第一次被访问，加入到访问历史列表；
                - 如果数据在访问历史列表里后没有达到K次访问，则按照一定规则（FIFO，LRU）淘汰；
                - 当访问历史队列中的数据访问次数达到K次后，将数据索引从历史队列删除，将数据移到缓存队列中，并缓存此数据，缓存队列重新按照时间排序；
                - 缓存数据队列中被再次访问后，重新排序；
                - 需要淘汰数据时，淘汰缓存队列中排在末尾的数据，即：淘汰“倒数第K次访问离现在最久”的数据。
            - LRU-K具有LRU的优点，同时能够避免LRU的缺点，实际应用中LRU-2是综合各种因素后最优的选择，LRU-3或者更大的K值命中率会高，但适应性差，需要大量的数据访问才能将历史访问记录清除掉。
    - Two queues（2Q）
        - 算法思想：
            - 该算法类似于LRU-2，不同点在于2Q将LRU-2算法中的访问历史队列（注意这不是缓存数据的）改为一个FIFO缓存队列，即：2Q算法有两个缓存队列，一个是FIFO队列，一个是LRU队列。
        - 工作原理：
            - 当数据第一次访问时，2Q算法将数据缓存在FIFO队列里面，当数据第二次被访问时，则将数据从FIFO队列移到LRU队列里面，两个队列各自按照自己的方法淘汰数据。详细实现如下：
            ![image](https://images2015.cnblogs.com/blog/472792/201611/472792-20161122232516175-1039348128.png)
                - 新访问的数据插入到FIFO队列；
                - 如果数据在FIFO队列中一直没有被再次访问，则最终按照FIFO规则淘汰；
                - 如果数据在FIFO队列中被再次访问，则将数据移到LRU队列头部；
                - 如果数据在LRU队列再次被访问，则将数据移到LRU队列头部；
                - LRU队列淘汰末尾的数据。


### 14. 讲讲你用Instrument优化动画性能的经历吧（别问我什么是Instrument）

> Apple的instrument为开发者提供了各种template去优化app性能和定位问题。很多公司都在赶feature，并没有充足的时间来做优化，导致不少开发者对instrument不怎么熟悉。但这里面其实涵盖了非常完整的计算机基础理论知识体系，memory，disk，network，thread，cpu，gpu等等，顺藤摸瓜去学习，是一笔巨大的知识财富。动画性能只是其中一个template，重点还是理解上面问题当中CPU GPU如何配合工作的知识。

[iOS app性能优化的那些事](https://www.jianshu.com/p/5cf9ac335aec)

[iOS app性能优化的那些事(二)](https://www.jianshu.com/p/2a01e5e2141f)

* Core Graphics 可以查看帧数... 像collectionview，tableview，mapview这样高速拖动的时候帧数50~60多是不错的...40多就略卡需要优化了...
* 优化的话，基础的的，reuse大家都知道，然后把opaque都设置为yes(有个选项可以显示那些为false的UIView)，然后把cornerRadius和shadow（主要是shadow）优化，不要用代码写。然后不要在delegate方法里使用类似 tableview.cellForIndexpath 还是 indexpathForCell 类似的方法 。
* 要求高一点，就尽可能缓存和预加载。而且不在delegate里减少需要计算的东西，和占内存的东西。VVebo有一个极致优化tableView的例子，是在后台进程先把layer的image绘制好，然后缓存起来要显示的时候再加载。


### 15. loadView是干嘛用的？

> 不要就简单的告诉我没用过，至少问下我有什么用。。这里是apple给开发者自己设置custom view的位置。说UI熟悉的一定要知道。

* 当你访问一个ViewController的view属性时，如果此时view的值是nil，那么，ViewController就会自动调用loadView这个方法。这个方法就会加载或者创建一个view对象，赋值给view属性。 
* loadView默认做的事情是：如果此ViewController存在一个对应的nib文件，那么就加载这个nib。否则，就创建一个UIView对象。
* 如果你用Interface Builder来创建界面，那么不应该重载这个方法。
* 如果你想自己创建view对象，那么可以重载这个方法。此时你需要自己给view属性赋值。你自定义的方法不应该调用super。如果你需要对view做一些其他的定制操作，在viewDidLoad里面去做。
* 有两种情况：
    - 如果你用了nib文件，重载这个方法就没有太大意义。因为loadView的作用就是加载nib。如果你重载了这个方法不调用super，那么nib文件就不会被加载。如果调用了super，那么view已经加载完了，你需要做的其他事情在viewDidLoad里面做更合适。
    - 如果你没有用nib，这个方法默认就是创建一个空的view对象。如果你想自己控制view对象的创建，例如创建一个特殊尺寸的view，那么可以重载这个方法，自己创建一个UIView对象，然后指定 self.view = myView; 但这种情况也没有必要调用super，因为反正你也不需要在super方法里面创建的view对象。如果调用了super，那么就是浪费了一些资源而已 


### 16. viewWillLayoutSubView你总是知道的。

> controller layout触发的时候，开发者有机会去重新layout自己的各个subview。说UI熟悉的一定要知道。

横竖屏切换的时候，系统会响应一些函数，其中 viewWillLayoutSubviews 和 viewDidLayoutSubviews。

```
- (void)viewWillLayoutSubviews

{

     [self _shouldRotateToOrientation:(UIDeviceOrientation)[UIApplication sharedApplication].statusBarOrientation];

}

-(void)_shouldRotateToOrientation:(UIDeviceOrientation)orientation {
        if (orientation == UIDeviceOrientationPortrait ||orientation ==
                UIDeviceOrientationPortraitUpsideDown) {
          // 竖屏
}
else {
         // 横屏
    }
}
```
通过上述一个函数就知道横竖屏切换的接口了。 

注意：viewWillLayoutSubviews只能用在ViewController里面，在view里面没有响应。


### 17. GCD里面有哪几种Queue？你自己建立过串行queue吗？背后的线程模型是什么样的？

> 两种queue，串行和并行。main queue是串行，global queue是并行。有些开发者为了在工作线程串行的处理任务会自己建立一个serial queue。背后是苹果维护的线程池，各种queue要用线程都是这个池子里取的。GCD大家都用过，但很多关键的概念不少人都理解的模凌两可。串行，并行，同步，异步是GCD的核心概念。

1.主队列 dispatch_main_queue(); 串行 ，更新UI 

2.全局队列 dispatch_global_queue(); 并行，四个优先级：background，low，default，high 

3.自定义队列 dispatch_queue_t queue ; 可以自定义是并行：DISPATCH_QUEUE_CONCURRENT或者串行DISPATCH_QUEUE_SERIAL

### 18. 用过coredata或者sqlite吗？读写是分线程的吗？遇到过死锁没？咋解决的？

> 没用过sqlite是说不过去的。用过CoreData的肯定有很多血泪史要说。多谢线程模型你肯定做过比较选择。死锁是啥肯定也是要知道的，没遇到过至少能举个简单的例子来说明。单个线程可以死锁（main thread里dispatch_sync到main queue），多个线程直接也可以死锁（A，B线程互相持有对方需要的资源且互相等待）。

[参考：CoreData与SQLite的线程安全](https://www.jianshu.com/p/95db3fc4deb3)

### 19. http的post和get啥区别？（区别挺多的，麻烦多说点）

> 这个可以说很多。不希望听到的答案有
两个差不多，随便用一个。
post比get安全（其实两个都不安全）
能说下两个http格式有什么不同，各自应用的场景就合格了。更多可以阅读下这个[答案](https://www.zhihu.com/question/31640769?rf=37401322)。

* Http定义了与服务器交互的不同方法，最基本的方法有4种，分别是GET，POST，PUT，DELETE。URL全称是资源描述符，我们可以这样认为：一个URL地址，它用于描述一个网络上的资源，而HTTP中的GET，POST，PUT，DELETE就对应着对这个资源的查，改，增，删4个操作。GET一般用于获取/查询资源信息，而POST一般用于更新资源信息。
* http中，GET用于信息获取，而且是幂等的。意味着该操作用于获取信息而非修改信息。换句话说，GET请求一般不产生副作用。就是说，它仅仅是获取资源信息，就像数据库查询一样，不会修改，增加数据，不会影响资源的状态。
* http中，POST是用于修改服务器上的资源的请求。
* get是从服务器上获取数据，post是向服务器传送数据。 
* get是把参数数据队列加到提交表单的ACTION属性所指的URL中，值和表单内各个字段一一对应，post是通过HTTP post机制，将表单内各个字段与其内容放置在HTML HEADER内一起传送到ACTION属性所指的URL地址。用户看不到这个过程。 
* 对于get方式，服务器端用Request.QueryString获取变量的值，对于post方式，服务器端用Request.Form获取提交的数据。 
* get安全性非常低，post安全性较高。但也只是高那么一点，如果没有加密，他们安全级别都是一样的，随便一个监听器都可以把所有的数据监听到。



### 20. 我知道你大学毕业过后就没接触过算法数据结构了，但是请你一定告诉我什么是Binary search tree? search的时间复杂度是多少？

> 很多人都很排斥数据结构和算法题，我个人意见是复杂的可以不知道，基础的一定要了解。时间复杂度是什么得知道，list，queue，stack，table，tree这些都要明白是啥。连hash表的概念都不知道怎么能保证在写代码的时候注意性能呢。

* Binary search tree:二叉搜索树。 
* 主要由四个方法：（用C语言实现或者Python） 
    1.search：时间复杂度为O(h)，h为树的高度

    2.traversal：时间复杂度为O(n)，n为树的总结点数。

    3.insert：时间复杂度为O(h)，h为树的高度。

    4.delete：最坏情况下，时间复杂度为O(h)+指针的移动开销。

可以看到，二叉搜索树的dictionary operation的时间复杂度与树的高度h相关。所以需要尽可能的降低树的高度，由此引出平衡二叉树Balanced binary tree。它要求左右两个子树的高度差的绝对值不超过1，并且左右两个子树都是一棵平衡二叉树。这样就可以将搜索树的高度尽量减小。


## 一份“有点难”的面试题
### 1. NSString如何计算字符的个数？
### 2. PKI体系当中加密和签名有什么区别？
### 3. 如何自己高效实现NSUserDefault?
### 4. 解释下tcp的慢启动特性。
### 5. 如何用HTTP实现长连接？
### 6. HTTP2.0针对同一个域名的多个请求，会建立多少个tcp连接？
### 7. 数据库建表的时候索引有什么用？
### 8. Full Text Search为什么快？
### 9. iOS下如何实现指定线程数目的线程池？
### 10. 介绍下iOS设备获取唯一设备号的历史变迁。
### 11. 函数式编程当中的 first-class function是什么意思呢？
### 12. 如何使用runtime hook一个class的某个方法，又如何hook某个instance的方法？
### 13. 谈下Objective C都有哪些锁机制，你一般用哪个？
### 14. 聊下HTTP post的body体使用form-urlencoded和multipart/form-data的区别。
### 15. 让你设计一种机制检测UIViewController的内存泄漏，你会怎么做？
### 16. 通过[UIImage imageNamed:]生成的对象什么时候被释放？
### 17. applicationWillEnterForeground和applicationDidBecomeActive都会在哪些场景下被调用？举例越多越好。
### 18. 如何终止正在运行的工作线程？
### 19. 穷举iOS下所有的本地持久化方案。
### 20. 如果公司强制996，你有什么心里话要对老板说吗？

## 补充一份基础的面试题
### 1. 在oc中如何实现深度拷贝
### 2. 请描述什么是delegate、block、NSNotification，他们有什么作用
### 3. 请写出一个线程安全的单例模式
### 4. 解释属性中strong、weak、assign、copy的区别
### 5. #import和#include的区别
### 6. 描述tableView的重用机制
### 7. Object-C有多继承吗？没有的话用什么代替？
### 8. category与继承之间的区别
### 9. #define和const定义的变量，有什么区别
### 10. TCP和UDP的区别是什么？
### 11. MD5和Base64的区别是什么，各自场景是什么？
### 12. 二叉搜索树的概念，时间复杂度多少？
### 13. 如何添加一个自定义字体到工程中
### 14. 如何制作一个静态库/动态库，他们的区别是什么？
### 15. Configuration中，debug和release的区别是什么？
### 16. push view controller 和 present view controller的区别
### 17. 描述下tableview cell的重用机制
### 18. UIView的frame和bounds的区别是什么
### 19. new与alloc init的区别
### 20. NSArray实例化时，array与init的区别
### 21. 哪些类不适合使用单例模式？即使他们在周期中只会出现一次。
### 22. Notification的使用场景是什么？同步还是异步？
### 23. 简单介绍一下KVC和KVO，他们都可以应用在哪些场景？
### 24. UIButton的父类是什么？UILabel呢？
### 25. 发送10个网络请求，然后再接收到所有回应之后执行后续操作，如何实现？
### 26. 实现一个第三方控件，可以在任何时候出现在APP界面最上层
### 27. 不同版本的APP，数据库结构变化了，如何处理?
### 28. 内存中的栈和堆的区别是什么？那些数据在栈上，哪些在堆上？
### 29. block中的weak self，是任何时候都需要加的么？
### 30. GCD的queue，main queue中执行的代码，一定是在main thread么？
### 31. NSOperationQueue有哪些使用方式
### 32. NSThread中的Runloop的作用，如何使用？
### 33. .h文件中的变量，外部可以直接访问么？（注意是变量，不是property）
### 34. 讲述一下runtime的概念，message send如果寻找不到相应的对象，会如何进行后续处理 ？
### 35. 利用runtime实现一个对象的拷贝

# 补充一份面试经验题
### 1. 说一下OC的反射机制；
### 2. block的实质是什么？有几种block？分别是怎样产生的？
### 3. __block修饰的变量为什么能在block里面能改变其值？
### 4. 说一下线程之间的通信。
### 5. 你们应用的崩溃率是多少？
### 6. 说一下hash算法。
### 7. NSDictionary的实现原理是什么？
### 8. 你们的App是如何处理本地数据安全的（比如用户名的密码）？
### 9. 遇到过BAD_ACCESS的错误吗？你是怎样调试的？
### 10. 什么是指针常量和常量指针？
### 11. 不借用第三个变量，如何交换两个变量的值？要求手动写出交换过程。
### 12. 若你去设计一个通知中心，你会怎样设计？
### 13. 如何去设计一个方案去应对后端频繁更改的字段接口？
### 14. KVO、KVC的实现原理
### 15. 用递归算法求1到n的和
### 16. category为什么不能添加属性？
### 17. 说一下runloop和线程的关系。
### 18. 说一下autoreleasePool的实现原理。
### 19. 说一下简单工厂模式，工厂模式以及抽象工厂模式？
### 20. 如何设计一个网络请求库？
### 21. 说一下多线程，你平常是怎么用的？
### 22. 说一下UITableViewCell的卡顿你是怎么优化的？
### 23. 看过哪些三方库？说一下实现原理以及好在哪里？
### 24. 说一下HTTP协议以及经常使用的code码的含义。
### 25. 设计一套缓存策略。
### 26. 设计一个检测主线和卡顿的方案。
### 27. 说一下runtime，工作是如何使用的？看过runtime源码吗？
### 28. 说几个你在工作中使用到的线程安全的例子。
### 29. 用过哪些锁？哪些锁的性能比较高？
### 30. 说一下HTTP和HTTPs的请求过程？
### 31. 说一下TCP和UDP
### 32. 说一下静态库和动态库之间的区别
### 33. load和initialize方法分别在什么时候调用的？
### 34. NSNotificationCenter是在哪个线程发送的通知？
### 35. 用过swift吗？如果没有，平常有学习吗？
### 36. 说一下你对架构的理解？
### 37. 为什么一定要在主线程里面更新UI？

# 知乎上面试题
### 1. 讲述一次在这个APP中，用户触发了一个事件，引起了一个服务请求，然后获取服务端返回，并且更新前端界面的过程。请说的详细一点，比如数据经过了哪些类的处理，每一次传递时的格式是怎么样的？
### 2. 你参与的APP，是如何处理多个服务的同步发起的？随后让面试者说一下APP的界面架构，这个比较随意。问完了项目，就开始基础知识题啦~
### Model层：
### 3. 数据持久化存储方案有哪些？
### 4. 沙盒的目录结构是怎样的？各自一般用于什么场合？
### 5. SQL语句问题：inner join、left join、right join的区别是什么？
### 6. sqlite的优化网络通信用过哪些方式（100%的人说了AFNetworking...）
### 7. 如何处理多个网络请求并发的情况
### 8. 在网络请求中如何提高性能
### 9. 在网络请求中如何保证安全性

## 语言与基础知识：
### 1. 内存中的栈和堆的区别是什么？
### 2. 那些数据在栈上，哪些在堆上？
### 3. #define和const定义的变量，有什么区别
### 4. 什么情况下会出现内存的循环引用block中的weak 
### 5. self，是任何时候都需要加的么？
### 6. GCD的queue，main queue中执行的代码，一定是在main thread么？
### 7. NSOperationQueue有哪些使用方式
### 8. NSThread中的Runloop的作用，如何使用？
### 9. .h文件中的变量，外部可以直接访问么？（注意是变量，不是property）
### 10. 讲述一下runtime的概念，
### 11. message send如果寻找不到相应的对象，会如何进行后续处理 ？
### 12. TCP和UDP的区别是什么？
### 13. MD5和Base64的区别是什么，各自场景是什么？
### 14. 二叉搜索树的概念，时间复杂度多少？架构：（我们招的不是架构师，这方面问的不多，而且从之前对APP的架构介绍里可以边听边问）哪些类不适合使用单例模式？即使他们在周期中只会出现一次。
### 15. Notification的使用场景是什么？同步还是异步？
### 16. 简单介绍一下KVC和KVO，他们都可以应用在哪些场景？

## APP相关：
### 1. 如何添加一个自定义字体到工程中
### 2. 如何制作一个静态库/动态库，他们的区别是什么？
### 3. Configuration中，debug和release的区别是什么？
### 4. 简单介绍下发送系统消息的机制（APNS） UI：系统如何寻找到需要响应用户操作的那个Responder
### 5. 多屏幕尺寸的适配
### 6. UIButton的父类是什么？UILabel呢？
### 7. push view controller 和 present view controller的区别
### 8. 描述下tableview cell的重用机制
### 9. UIView的frame和bounds的区别是什么 
### 10. 发送10个网络请求，然后再接收到所有回应之后执行后续操作，如何实现？
### 11. 实现一个第三方控件，可以在任何时候出现在APP界面最上层
### 12. 实现一个最简单的点击拖拽功能。上面那个拖拽之外，如果在手放开时，需要根据速度往前滑动呢？
### 13. 如何减小一个应用程序的尺寸？
### 14. 如何提高一个性用程序的性能？
### 15. 不同版本的APP，数据库结构变化了，如何处理?
