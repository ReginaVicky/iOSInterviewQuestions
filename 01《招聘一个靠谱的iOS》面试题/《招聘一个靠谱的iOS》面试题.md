# iOSInterviewQuestion
## 招聘一个靠谱的iOS面试题（附答案）
- 01[《招聘一个靠谱的iOS》](http://blog.sunnyxx.com/2015/07/04/ios-interview/)面试题，面试题来源是微博[@我就叫Sunny怎么了](https://weibo.com/u/1364395395)的这篇博文：[《招聘一个靠谱的 iOS》](http://blog.sunnyxx.com/2015/07/04/ios-interview/)，其中共55题，除第一题为纠错题外，其他54道均为简答题。出题者简介： 孙源（sunnyxx），目前就职于百度，负责百度知道 iOS 客户端的开发工作，对技术喜欢刨根问底和总结最佳实践，热爱分享和开源，维护一个叫 forkingdog 的开源小组。
- 如有纰漏，请向微博[@爱吃兔兔的胡萝卜吖](https://weibo.com/6447187962/)反馈。


# 索引

1.[风格纠错题](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#1风格纠错题)

- [优化部分](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md)<br>

- [硬伤部分](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md)

2.[@property后面可以有哪些修饰符?](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#2property-后面可以有哪些修饰符)

3.[什么情况使用weak关键字,相比assign有什么不同？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#3什么情况使用-weak-关键字相比-assign-有什么不同)

4.[怎么用copy关键字？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#4怎么用-copy-关键字)

5.[这个写法会出什么问题： @property (copy) NSMutableArray *array;](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#5这个写法会出什么问题-property-copy-nsmutablearray-array)

6.[如何让自己的类用 copy 修饰符？如何重写带 copy 关键字的 setter？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#6如何让自己的类用copy修饰符如何重写带-copy-关键字的-setter)

7.[@property 的本质是什么？ivar、getter、setter 是如何生成并添加到这个类中的](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#7property-的本质是什么ivargettersetter-是如何生成并添加到这个类中的)

8.[@protocol 和 category 中如何使用 @property](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#8protocol-和-category-中如何使用-property)

9.[runtime 如何实现 weak 属性](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#9runtime-如何实现-weak-属性)

10.[@property中有哪些属性关键字？/ @property 后面可以有哪些修饰符？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#10property中有哪些属性关键字-property-后面可以有哪些修饰符)

11.[weak属性需要在dealloc中置nil么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#11weak属性需要在dealloc中置nil么)

12.[@synthesize和@dynamic分别有什么作用？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#12synthesize和dynamic分别有什么作用)

13.[ARC下，不显式指定任何属性关键字时，默认的关键字都有哪些？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#13arc下不显式指定任何属性关键字时默认的关键字都有哪些)

14.[用@property声明的NSString（或NSArray，NSDictionary）经常使用copy关键字，为什么？如果改用strong关键字，可能造成什么问题？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#14用property声明的nsstring或nsarraynsdictionary经常使用copy关键字为什么如果改用strong关键字可能造成什么问题)

15.[@synthesize合成实例变量的规则是什么？假如property名为foo，存在一个名为_foo的实例变量，那么还会自动合成新变量么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#15synthesize合成实例变量的规则是什么假如property名为foo存在一个名为_foo的实例变量那么还会自动合成新变量么)

16.[在有了自动合成属性实例变量之后，@synthesize还有哪些使用场景？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#16在有了自动合成属性实例变量之后synthesize还有哪些使用场景)

17.[objc中向一个nil对象发送消息将会发生什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#17objc中向一个nil对象发送消息将会发生什么)

18.[objc中向一个对象发送消息[obj foo]和objc_msgSend()函数之间有什么关系？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#18objc中向一个对象发送消息obj-foo和objc_msgsend函数之间有什么关系)

19.[什么时候会报unrecognized selector的异常？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#19什么时候会报unrecognized-selector的异常)

20.[一个objc对象如何进行内存布局？（考虑有父类的情况）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#20一个objc对象如何进行内存布局考虑有父类的情况)

21.[一个objc对象的isa的指针指向什么？有什么作用？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#21一个objc对象的isa的指针指向什么有什么作用)

22.[下面的代码输出什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#22下面的代码输出什么)

```
Objective-C
	@implementation Son : Father
	- (id)init
	{
	    self = [super init];
	    if (self) {
	        NSLog(@"%@", NSStringFromClass([self class]));
	        NSLog(@"%@", NSStringFromClass([super class]));
	    }
	    return self;
	}
	@end
```
23.[`_objc_msgForward` 函数是做什么的，直接调用它将会发生什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#23_objc_msgforward-函数是做什么的直接调用它将会发生什么)

24.[runtime如何实现weak变量的自动置nil？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#24runtime如何实现weak变量的自动置nil)

25.[能否向编译后得到的类中增加实例变量？能否向运行时创建的类中添加实例变量？为什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#25能否向编译后得到的类中增加实例变量能否向运行时创建的类中添加实例变量为什么)

26.[runloop和线程有什么关系？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#26runloop和线程有什么关系)

27.[runloop的mode作用是什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#27runloop的mode作用是什么)

28.[以+ scheduledTimerWithTimeInterval...的方式触发的timer，在滑动页面上的列表时，timer会暂定回调，为什么？如何解决？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#28以-scheduledtimerwithtimeinterval的方式触发的timer在滑动页面上的列表时timer会暂定回调为什么如何解决)

29.[猜想runloop内部是如何实现的？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#29猜想runloop内部是如何实现的)

30.[objc使用什么机制管理对象内存？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#30objc使用什么机制管理对象内存)

31.[ARC通过什么方式帮助开发者管理内存？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#31arc通过什么方式帮助开发者管理内存)

32.[不手动指定autoreleasepool的前提下，一个autorealese对象在什么时刻释放？（比如在一个vc的viewDidLoad中创建）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#32不手动指定autoreleasepool的前提下一个autorealese对象在什么时刻释放比如在一个vc的viewdidload中创建)

33.[BAD_ACCESS在什么情况下出现？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#33bad_access在什么情况下出现)

34.[苹果是如何实现autoreleasepool的？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#34苹果是如何实现autoreleasepool的)

35.[使用block时什么情况会发生引用循环，如何解决？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#35使用block时什么情况会发生引用循环如何解决)

36.[在block内如何修改block外部变量？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#36在block内如何修改block外部变量)

37.[使用系统的某些block api（如UIView的block版本写动画时），是否也考虑引用循环问题？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#37使用系统的某些block-api如uiview的block版本写动画时是否也考虑引用循环问题)

48.[GCD的队列（dispatch_queue_t）分哪两种类型？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#38gcd的队列dispatch_queue_t分哪两种类型)

39.[如何用GCD同步若干个异步调用？（如根据若干个url异步加载多张图片，然后在都下载完成后合成一张整图）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#39如何用gcd同步若干个异步调用如根据若干个url异步加载多张图片然后在都下载完成后合成一张整图)

40.[dispatch_barrier_async的作用是什么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#40dispatch_barrier_async的作用是什么)

41.[苹果为什么要废弃dispatch_get_current_queue？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#41苹果为什么要废弃dispatch_get_current_queue)

42. [以下代码运行结果如何？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#42以下代码运行结果如何)

```Objective-C
- (void)viewDidLoad
{
    [super viewDidLoad];
    NSLog(@"1");
    dispatch_sync(dispatch_get_main_queue(), ^{
        NSLog(@"2");
    });
    NSLog(@"3");
}
 ```
43.[addObserver:forKeyPath:options:context:各个参数的作用分别是什么，observer中需要实现哪个方法才能获得KVO回调？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#43addobserverforkeypathoptionscontext各个参数的作用分别是什么observer中需要实现哪个方法才能获得kvo回调)

44.[如何手动触发一个value的KVO](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#44如何手动触发一个value的kvo)

45.[若一个类有实例变量 NSString *_foo ，调用setValue:forKey:时，可以以foo还是 _foo 作为key？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#45若一个类有实例变量-nsstring-_foo-调用setvalueforkey时可以以foo还是-_foo-作为key)

46.[KVC的keyPath中的集合运算符如何使用？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#46kvc的keypath中的集合运算符如何使用)

47.[KVC和KVO的keyPath一定是属性么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#47kvc和kvo的keypath一定是属性么)

48.[如何关闭默认的KVO的默认实现，并进入自定义的KVO实现？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#48如何关闭默认的kvo的默认实现并进入自定义的kvo实现)

49.[apple用什么方式实现对一个对象的KVO？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#49apple用什么方式实现对一个对象的kvo)

50.[IBOutlet连出来的视图属性为什么可以被设置成weak?](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#50iboutlet连出来的视图属性为什么可以被设置成weak)

51.[IB中User Defined Runtime Attributes如何使用？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#51ib中user-defined-runtime-attributes如何使用)

52.[如何调试BAD_ACCESS错误](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#52如何调试bad_access错误)

53.[lldb（gdb）常用的调试命令？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#53-lldbgdb常用的调试命令)

## 1.风格纠错题
![image](https://camo.githubusercontent.com/748813155b831969a3ff5829f527b851d1b6c8a9/687474703a2f2f692e696d6775722e636f6d2f4f375a657639342e706e67)

## 2.@property 后面可以有哪些修饰符？

## 3.什么情况使用 weak 关键字，相比 assign 有什么不同？

## 4.怎么用 copy 关键字？

## 5.这个写法会出什么问题： @property (copy) NSMutableArray *array;

## 6.如何让自己的类用copy修饰符？如何重写带 copy 关键字的 setter？

## 7.@property 的本质是什么？ivar、getter、setter 是如何生成并添加到这个类中的

## 8.@protocol 和 category 中如何使用 @property

## 9.runtime 如何实现 weak 属性

## 10.@property中有哪些属性关键字？/ @property 后面可以有哪些修饰符

## 11.weak属性需要在dealloc中置nil么？

## 12.@synthesize和@dynamic分别有什么作用？

## 13.ARC下，不显式指定任何属性关键字时，默认的关键字都有哪些？

## 14.用@property声明的NSString（或NSArray，NSDictionary）经常使用copy关键字，为什么？如果改用strong关键字，可能造成什么问题？

## 15.@synthesize合成实例变量的规则是什么？假如property名为foo，存在一个名为_foo的实例变量，那么还会自动合成新变量么？

## 16.在有了自动合成属性实例变量之后，@synthesize还有哪些使用场景？

## 17.objc中向一个nil对象发送消息将会发生什么？

## 18.objc中向一个对象发送消息[obj foo]和objc_msgSend()函数之间有什么关系？

## 19.什么时候会报unrecognized selector的异常？

## 20.一个objc对象如何进行内存布局？（考虑有父类的情况）

## 21.一个objc对象的isa的指针指向什么？有什么作用？

## 22.下面的代码输出什么？

```
Objective-C
	@implementation Son : Father
	- (id)init
	{
	    self = [super init];
	    if (self) {
	        NSLog(@"%@", NSStringFromClass([self class]));
	        NSLog(@"%@", NSStringFromClass([super class]));
	    }
	    return self;
	}
	@end
```

## 23.`_objc_msgForward` 函数是做什么的，直接调用它将会发生什么？

## 24.runtime如何实现weak变量的自动置nil？

## 25.能否向编译后得到的类中增加实例变量？能否向运行时创建的类中添加实例变量？为什么？

## 26.runloop和线程有什么关系？

## 27.runloop的mode作用是什么？

## 28.以+ scheduledTimerWithTimeInterval...的方式触发的timer，在滑动页面上的列表时，timer会暂定回调，为什么？如何解决？

## 29.猜想runloop内部是如何实现的？

## 30.objc使用什么机制管理对象内存？

## 31.ARC通过什么方式帮助开发者管理内存？

## 32.不手动指定autoreleasepool的前提下，一个autorealese对象在什么时刻释放？（比如在一个vc的viewDidLoad中创建）

## 33.BAD_ACCESS在什么情况下出现？

## 34.苹果是如何实现autoreleasepool的？

## 35.使用block时什么情况会发生引用循环，如何解决？

## 36.在block内如何修改block外部变量？

## 37.使用系统的某些block api（如UIView的block版本写动画时），是否也考虑引用循环问题？

## 38.GCD的队列（dispatch_queue_t）分哪两种类型？

## 39.如何用GCD同步若干个异步调用？（如根据若干个url异步加载多张图片，然后在都下载完成后合成一张整图）

## 40.dispatch_barrier_async的作用是什么？

## 41.苹果为什么要废弃dispatch_get_current_queue？

## 42.以下代码运行结果如何？

```
Objective-C
- (void)viewDidLoad
{
    [super viewDidLoad];
    NSLog(@"1");
    dispatch_sync(dispatch_get_main_queue(), ^{
        NSLog(@"2");
    });
    NSLog(@"3");
}
```

## 43.addObserver:forKeyPath:options:context:各个参数的作用分别是什么，observer中需要实现哪个方法才能获得KVO回调？

## 44.如何手动触发一个value的KVO

## 45.若一个类有实例变量 NSString *_foo ，调用setValue:forKey:时，可以以foo还是 _foo 作为key？

## 46.KVC的keyPath中的集合运算符如何使用？

## 47.KVC和KVO的keyPath一定是属性么？

## 48.如何关闭默认的KVO的默认实现，并进入自定义的KVO实现？

## 49.apple用什么方式实现对一个对象的KVO？

## 50.IBOutlet连出来的视图属性为什么可以被设置成weak?

## 51.IB中User Defined Runtime Attributes如何使用？

## 52.如何调试BAD_ACCESS错误

## 53. lldb（gdb）常用的调试命令？
