# iOSInterviewQuestion
## 招聘一个靠谱的iOS面试题（附答案）
- 01[《招聘一个靠谱的iOS》](http://blog.sunnyxx.com/2015/07/04/ios-interview/)面试题，面试题来源是微博[@我就叫Sunny怎么了](https://weibo.com/u/1364395395)的这篇博文：[《招聘一个靠谱的 iOS》](http://blog.sunnyxx.com/2015/07/04/ios-interview/)，其中共55题，除第一题为纠错题外，其他54道均为简答题。出题者简介： 孙源（sunnyxx），目前就职于百度，负责百度知道 iOS 客户端的开发工作，对技术喜欢刨根问底和总结最佳实践，热爱分享和开源，维护一个叫 forkingdog 的开源小组。
- 如有纰漏，请向微博[@爱吃兔兔的胡萝卜吖](https://weibo.com/6447187962/)反馈。


# 索引

1.[风格纠错题](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#1风格纠错题)

- [硬伤部分](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md)<br>

- [优化部分](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md)

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

### 硬伤部分
1. 在-和(void)之间应该有一个空格
2. enum 中驼峰命名法和下划线命名法混用错误：枚举类型的命名规则和函数的命名规则相同：命名时使用驼峰命名法，勿使用下划线命名法。
3. enum 左括号前加一个空格，或者将左括号换到下一行
4. enum 右括号后加一个空格
5. UserModel :NSObject 应为UserModel : NSObject，也就是:右侧少了一个空格。
6. @interface 与 @property 属性声明中间应当间隔一行。
7. 两个方法定义之间不需要换行，有时为了区分方法的功能也可间隔一行，但示例代码中间隔了两行。
8. -(id)initUserModelWithUserName: (NSString*)name withAge:(int)age; 方法中方法名与参数之间多了空格。而且 - 与 (id) 之间少了空格。
9. -(id)initUserModelWithUserName: (NSString*)name withAge:(int)age; 方法中方法名与参数之间多了空格：(NSString*)name 前多了空格。
10. -(id)initUserModelWithUserName: (NSString*)name withAge:(int)age; 方法中 (NSString*)name,应为 (NSString *)name，少了空格。

### 优化部分


## 2.@property 后面可以有哪些修饰符？

- 常用的修饰符有4类：
    * readonly,readwrite表示读写全线
    * retain,copy,assign,strong,weak表示引用方式,涉及属性自动创建的setter的实现
    * nonatomic,atomic意为原子特性,表示是否线程安全.
    * getter,setter表示自定义的获取/设置方法.

## 3.什么情况使用 weak 关键字，相比 assign 有什么不同？

- 什么情况使用weak关键字
    * 在ARC模式下，在有可能出现循环引用时，让其一端使用weak修饰。例如：delegate（代理）属性；
    * 自身已经对它强引用一次了，没有必再强引用一次使用weak解决。例如：自定义IBOutlet控件属性。当然，也可以使用strong。
 
- 相比assign有什么不同
    * weak只能用于修饰对象类型，基本数据类型不能使用，weak的特质表明，该属性定义了一种“非拥有关系” (nonowning relationship)。为这种属性设置新值时，设置方法既不保留新值，也不释放旧值。此特质同assign类似， 但是在属性所指向的对象被摧毁时，属性值也会清空(nil out)。但是assign的“设置方法”只会执行针对“纯量类型” (scalar type，例如 CGFloat 或 NSlnteger 等)的简单赋值操作。
    * assign 可以用非 OC 对象,而 weak 必须用于 OC 对象。
    * ==注意:assign修饰的对象（一般编译的时候会产生警告：Assigning retained object to unsafe property; object will be released after assignment）在释放之后，指针的地址还是存在的，也就是说指针并没有被置为nil，造成野指针。对象一般分配在堆上的某块内存，如果在后续的内存分配中，刚好分到了这块地址，程序就会崩溃掉。那为什么可以用assign修饰基本数据类型？因为基础数据类型一般分配在栈上，栈的内存会由系统自己自动处理，不会造成野指针。weak修饰的对象在释放之后，指针地址会被置为nil。所以现在一般弱引用就是用weak。==



## 4.怎么用 copy 关键字？

## 5.这个写法会出什么问题： @property (copy) NSMutableArray *array;

- 两个问题：
    * 1、添加,删除,修改数组内的元素的时候,程序会因为找不到对应的实例方法而崩溃.报
```
-[__NSArrayI addObject:]: unrecognized selector sent to instance 0x7ff240614b40
```
错误，因为 copy 就是复制一个不可变 NSArray 的对象；

 - - 2、使用了 atomic 属性会严重影响性能 ；

- 具体分析：
    * 第一个原因：copy 此特质所表达的所属关系与 strong 类似。然而设置方法并不保留新值，而是将其“拷贝” (copy)。 当属性类型为 NSString（或NSArray，NSDictionary） 时，经常用此特质来保护其封装性，因为传递给设置方法的新值有可能指向一个 NSMutableString（或NSMutableArray，NSMutableDictionary） 类的实例。这个类是 NSString（或NSArray，NSDictionary） 的子类，表示一种可修改其值的字符串，此时若是不拷贝字符串，那么设置完属性之后，字符串的值就可能会在对象不知情的情况下遭人更改。所以，这时就要拷贝一份“不可变” (immutable)的字符串，确保对象中的字符串值不会无意间变动。只要实现属性所用的对象是“可变的” (mutable)，就应该在设置新属性值时拷贝一份。所以使用copy 就是复制一个不可变 NSArray 的对象；所以会报找不到对应的实例方法而崩溃。
    * 第二个原因：该属性使用了同步锁，会在创建时生成一些额外的代码用于帮助编写多线程程序，这会带来性能问题，通过声明 nonatomic 可以节省这些虽然很小但是不必要额外开销。在默认情况下，由编译器所合成的方法会通过锁定机制确保其原子性(atomicity)。如果属性具备 nonatomic 特质，则不使用同步锁。请注意，尽管没有名为“atomic”的特质(如果某属性不具备 nonatomic 特质，那它就是“原子的”(atomic))。在iOS开发中，你会发现，几乎所有属性都声明为 nonatomic。一般情况下并不要求属性必须是“原子的”，因为这并不能保证“线程安全” ( thread safety)，若要实现“线程安全”的操作，还需采用更为深层的锁定机制才行。例如，一个线程在连续多次读取某属性值的过程中有别的线程在同时改写该值，那么即便将属性声明为 atomic，也还是会读到不同的属性值。因此，开发iOS程序时一般都会使用 nonatomic 属性。但是在开发 Mac OS X 程序时，使用 atomic 属性通常都不会有性能瓶颈。

## 6.如何让自己的类用copy修饰符？如何重写带 copy 关键字的 setter？

## 7.@property 的本质是什么？ivar、getter、setter 是如何生成并添加到这个类中的

## 8.@protocol 和 category 中如何使用 @property

- category和protocol都可以添加方法，也都可以添加@property 关键字

- 在 protocol 中使用 property 只会生成 setter 和 getter 方法声明,我们使用属性的目的,是希望遵守我协议的对象能实现该属性，也就是说，在实现这个protocol协议的类中，我们要自己手动添加实例变量，并且需要实现setter和getter方法

- category 使用 @property 也是只会生成 setter 和 getter 方法的声明,由于category不能添加实例变量，故必须通过运行时添加associated object的方法来添加实例变量，如果我们真的需要给 category 增加属性的实现,需要借助于运行时的两个函数：

    * objc_setAssociatedObject

    * objc_getAssociatedObject

## 9.runtime 如何实现 weak 属性


## 10.@property中有哪些属性关键字？/ @property 后面可以有哪些修饰符

- 属性可以拥有的特质分为四类:

    * 原子性--- nonatomic 特质
    
        在默认情况下，由编译器合成的方法会通过锁定机制确保其原子性(atomicity)。如果属性具备 nonatomic 特质，则不使用自旋锁。请注意，尽管没有名为“atomic”的特质(如果某属性不具备 nonatomic 特质，那它就是“原子的” ( atomic) )，但是仍然可以在属性特质中写明这一点，编译器不会报错。若是自己定义存取方法，那么就应该遵从与属性特质相符的原子性。

    * 读/写权限---readwrite(读写)、readonly (只读)

    * 内存管理语义---assign、strong、 weak、unsafe_unretained、copy

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

## 11.weak属性需要在dealloc中置nil么？

## 12.@synthesize和@dynamic分别有什么作用？


## 13.ARC下，不显式指定任何属性关键字时，默认的关键字都有哪些？

- 对应基本数据类型默认关键字是
atomic,readwrite,assign 
- 对于普通的 Objective-C 对象 atomic,readwrite,strong


## 14.用@property声明的NSString（或NSArray，NSDictionary）经常使用copy关键字，为什么？如果改用strong关键字，可能造成什么问题？

## 15.@synthesize合成实例变量的规则是什么？假如property名为foo，存在一个名为_foo的实例变量，那么还会自动合成新变量么？

## 16.在有了自动合成属性实例变量之后，@synthesize还有哪些使用场景？

## 17.objc中向一个nil对象发送消息将会发生什么？

## 18.objc中向一个对象发送消息[obj foo]和objc_msgSend()函数之间有什么关系？

## 19.什么时候会报unrecognized selector的异常？

## 20.一个objc对象如何进行内存布局？（考虑有父类的情况）

## 21.一个objc对象的isa的指针指向什么？有什么作用？

- sa指针是什么？
    * 我们经常使用id来声明一个对象，本质上，我们创建的一个对象或实例其实就是一个struct objc_object结构体，而我们常用的id也就是这个结构体的指针。这个结构体只有一个成员变量，这是一个Class类型的变量isa，也是一个结构体									指针。面向对象中每一个对象都必须依赖一个类来创建，因此对象的isa指针就指向对象所属的类根据这个类模板能够创建出实例变量、实例方法等。
- 对象的isa指针
    * 每个实例对象有个isa的指针,他指向对象的类
- 类对象的isa指针
    * Class里也有个isa的指针, 指向meteClass(元类)。
- 元类的isa指针
    * 元类保存了类方法的列表。当类方法被调用时，先会从本身查找类方法的实现，如果没有，元类会向他父类查找该方法。同时注意的是：元类（meteClass）也是类，它也是对象。元类也有isa指针,它的isa指针最终指向的是一个根元类(root meteClass).根元类的isa指针指向本身，这样形成了一个封闭的内循环。

![image](http://img.zhimengzhe.com/d/file/p/2017-03-23/8c3150b91893bfef8b2f925d986388d6.png)

![image](http://hi.csdn.net/attachment/201201/19/0_1326963670oeC1.gif)

参考文献：
- [《iOS class深入理解： 实例对象、类对象、元类和isa指针》](http://www.zhimengzhe.com/IOSkaifa/253119.html)
- [《iOS中isa指针》](https://blog.csdn.net/miao_em/article/details/56671616)

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

- 不能向编译后得到的类中增加实例变量；
- 能向运行时创建的类中添加实例变量；
解释下：
- 原因：
    * 因为编译后的类已经注册在 runtime 中，类结构体中的 objc_ivar_list 实例变量的链表 和 instance_size 实例变量的内存大小已经确定，同时runtime 会调用 class_setIvarLayout 或 class_setWeakIvarLayout 来处理 strong weak 引用。所以不能向存在的类中添加实例变量；
    * 运行时创建的类是可以添加实例变量，调用 class_addIvar 函数。但是得在调用 objc_allocateClassPair 之后，objc_registerClassPair 之前，原因同上。

## 26.runloop和线程有什么关系？

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


## 27.runloop的mode作用是什么？

- model主要是用来指定事件在运行循环中的优先级的，分为：
    * NSDefaultRunLoopMode（kCFRunLoopDefaultMode）：默认，空闲状态
    * UITrackingRunLoopMode：ScrollView滑动时
    * UIInitializationRunLoopMode：启动时
    * NSRunLoopCommonModes（kCFRunLoopCommonModes）：Mode集合
- 苹果公开提供的 Mode 有两个：
    * NSDefaultRunLoopMode（kCFRunLoopDefaultMode）
    * NSRunLoopCommonModes（kCFRunLoopCommonModes）

## 28.以+ scheduledTimerWithTimeInterval...的方式触发的timer，在滑动页面上的列表时，timer会暂定回调，为什么？如何解决？

## 29.猜想runloop内部是如何实现的？

> 一般来讲，一个线程一次只能执行一个任务，执行完成后线程就会退出。如果我们需要一个机制，让线程能随时处理事件但并不退出，通常的代码逻辑 是这样的：


```
function loop() {
    initialize();
    do {
        var message = get_next_message();
        process_message(message);
    } while (message != quit);
}
```
或使用伪代码来展示下:

```
// 
// http://weibo.com/luohanchenyilong/ (微博@iOS程序犭袁)
// https://github.com/ChenYilong
int main(int argc, char * argv[]) {
 //程序一直运行状态
 while (AppIsRunning) {
      //睡眠状态，等待唤醒事件
      id whoWakesMe = SleepForWakingUp();
      //得到唤醒事件
      id event = GetEvent(whoWakesMe);
      //开始处理事件
      HandleEvent(event);
 }
 return 0;
}
```
参考文献：
- [《深入理解RunLoop》](https://blog.ibireme.com/2015/05/18/runloop/#base)
- [CFRunLoop](https://github.com/ming1016/study/wiki/CFRunLoop)，原作者是微博@我就叫Sunny怎么了


## 30.objc使用什么机制管理对象内存？

- 通过 retainCount 的机制来决定对象是否需要释放。 每次 runloop 的时候，都会检查对象的retainCount，如果retainCount为0，说明该对象没有地方需要继续使用了，可以释放掉了。

## 31.ARC通过什么方式帮助开发者管理内存？


## 32.不手动指定autoreleasepool的前提下，一个autorealese对象在什么时刻释放？（比如在一个vc的viewDidLoad中创建）

- 分两种情况：手动干预释放时机、系统自动去释放。
    * 手动干预释放时机--指定autoreleasepool 就是所谓的：当前作用域大括号结束时释放。
    * 系统自动去释放--不手动指定autoreleasepool
- Autorelease对象出了作用域之后，会被添加到最近一次创建的自动释放池中，并会在当前的 runloop 迭代结束时释放。释放的时机总结起来，可以用下图来表示：

![image](https://camo.githubusercontent.com/56f8ea718f47679e7771d247d8f6f820de2e0ab5/687474703a2f2f6936312e74696e797069632e636f6d2f32386b6f6477702e6a7067)

下面对这张图进行详细的解释：

- 从程序启动到加载完成是一个完整的运行循环，然后会停下来，等待用户交互，用户的每一次交互都会启动一次运行循环，来处理用户所有的点击事件、触摸事件。
- 我们都知道： 所有 autorelease 的对象，在出了作用域之后，会被自动添加到最近创建的自动释放池中。
- 但是如果每次都放进应用程序的 main.m 中的 autoreleasepool 中，迟早有被撑满的一刻。这个过程中必定有一个释放的动作。何时？在一次完整的运行循环结束之前，会被销毁。
- 那什么时间会创建自动释放池？运行循环检测到事件并启动后，就会创建自动释放池。
- 子线程的 runloop 默认是不工作，无法主动创建，必须手动创建。
- 自定义的 NSOperation 和 NSThread 需要手动创建自动释放池。比如： 自定义的 NSOperation 类中的 main 方法里就必须添加自动释放池。否则出了作用域后，自动释放对象会因为没有自动释放池去处理它，而造成内存泄露。
- 但对于 blockOperation 和 invocationOperation 这种默认的Operation ，系统已经帮我们封装好了，不需要手动创建自动释放池。
- @autoreleasepool 当自动释放池被销毁或者耗尽时，会向自动释放池中的所有对象发送 release 消息，释放自动释放池中的所有对象。
- 如果在一个vc的viewDidLoad中创建一个 Autorelease对象，那么该对象会在 viewDidAppear 方法执行前就被销毁了。
- 参考链接：[《黑幕背后的Autorelease》](http://blog.sunnyxx.com/2014/10/15/behind-autorelease/)



## 33.BAD_ACCESS在什么情况下出现？

- 访问了悬垂指针，比如对一个已经释放的对象执行了release、访问已经释放对象的成员变量或者发消息。 
- 死循环

## 34.苹果是如何实现autoreleasepool的？

- autoreleasepool 以一个队列数组的形式实现,主要通过下列三个函数完成.
    * objc_autoreleasepoolPush
    * objc_autoreleasepoolPop
    * objc_autorelease
    
看函数名就可以知道，对 autorelease 分别执行 push，和 pop 操作。销毁对象时执行release操作。
- 举例说明：我们都知道用类方法创建的对象都是 Autorelease 的，那么一旦 Person 出了作用域，当在 Person 的 dealloc 方法中打上断点，我们就可以看到这样的调用堆栈信息

![image](https://camo.githubusercontent.com/1e77679169328e5128722b3268bf9a488fc00ae2/687474703a2f2f6936302e74696e797069632e636f6d2f31356d666a31312e6a7067)

## 35.使用block时什么情况会发生引用循环，如何解决？

- 循环引用就是当self 拥有一个block的时候，在block 又调用self的方法。形成你中有我，我中有你，谁都无法将谁释放的困局。其实就是一个对象中强引用了block，在block中又强引用了该对象，就会发生循环引用。

```
self.myBlock = ^{
    [self doSomething];
  };
       +-----------+           +-----------+
       |    self   |           |   Block   |
  ---> |           | --------> |           |
       | retain 2  | <-------- | retain 1  |
       |           |           |           |
       +-----------+           +-----------+

```
又或者
```
ClassA* objA = [[[ClassA alloc] init] autorelease];
  objA.myBlock = ^{
    [self doSomething];
  };
  self.objA = objA;

  +-----------+           +-----------+           +-----------+
  |   self    |           |   objA    |           |   Block   |
  |           | --------> |           | --------> |           |
  | retain 1  |           | retain 1  |           | retain 1  |
  |           |           |           |           |           |
  +-----------+           +-----------+           +-----------+
       ^                                                |
       |                                                |
       +------------------------------------------------+

```

- 解决方法是将该对象使用__weak或者__block修饰符修饰之后再在block中使用。
    * id weak weakSelf = self; 或者 weak __typeof(&*self)weakSelf = self该方法可以设置宏
    * id __block weakSelf = self;
    * 或者将其中一方强制制空 xxx = nil。

```
__weak typeof (self) weakSelf = self;
［self.button  ^｛
      weakSelf.label.text = @"I am Label";
 }］;

//这个时候就变成这样了。
  +-----------+           +-----------+           +-----------+
  |   self    |           |  button   |           |   Block   |
  |           | --------> |           | --------> |           |
  | retain 1  |           | retain 1  |           | retain 1  |
  |           |           |           |           |           |
  +-----------+           +-----------+           +-----------+
       ^                                                |
       |                                                |
       + - - - - - - - - - - - - - - - - - - - - - - - -+
                               weak

```
- 检测代码中是否存在循环引用问题，可使用 Facebook 开源的一个检测工具[FBRetainCycleDetector](https://github.com/facebook/FBRetainCycleDetector) 。


## 36.在block内如何修改block外部变量？

## 37.使用系统的某些block api（如UIView的block版本写动画时），是否也考虑引用循环问题？

- 系统的某些block api中，UIView的block版本写动画时不需要考虑，但也有一些api 需要考虑：
- 所谓“引用循环”是指双向的强引用，所以那些“单向的强引用”（block 强引用 self ）没有问题，比如这些：

```
[UIView animateWithDuration:duration animations:^{ [self.superview layoutIfNeeded]; }]; 
```

```
[[NSOperationQueue mainQueue] addOperationWithBlock:^{ self.someProperty = xyz; }]; 
```

```
[[NSNotificationCenter defaultCenter] addObserverForName:@"someNotification" 
                                                 object:nil 
                          queue:[NSOperationQueue mainQueue]
                                             usingBlock:^(NSNotification * notification) {
                                                   self.someProperty = xyz; }]; 
```
这些情况不需要考虑“引用循环”。

但如果你使用一些参数中可能含有 ivar 的系统 api ，如 GCD 、NSNotificationCenter就要小心一点：比如GCD 内部如果引用了 self，而且 GCD 的其他参数是 ivar，则要考虑到循环引用：

```
__weak __typeof__(self) weakSelf = self;
dispatch_group_async(_operationsGroup, _operationsQueue, ^
{
__typeof__(self) strongSelf = weakSelf;
[strongSelf doSomething];
[strongSelf doSomethingElse];
} );
```
类似的

```
__weak __typeof__(self) weakSelf = self;
 _observer = [[NSNotificationCenter defaultCenter] addObserverForName:@"testKey"
                                                               object:nil
                                                                queue:nil
                                                           usingBlock:^(NSNotification *note) {
     __typeof__(self) strongSelf = weakSelf;
     [strongSelf dismissModalViewControllerAnimated:YES];
 }];

```
- self --> _observer --> block --> self 显然这也是一个循环引用。
- 总结：所谓循环引用，是因为当前控制器在引用着block，而block又引用着self即当前控制器，这样就造成了循环引用。系统的block或者AFN等block的调用并不在当前控制器中调用，那么这个self就不代表当前控制器，那自然也就没有循环引用的问题。

## 38.GCD的队列（dispatch_queue_t）分哪两种类型？

- 串行队列Serial Dispatch Queue
- 并行队列Concurrent Dispatch Queue

## 39.如何用GCD同步若干个异步调用？（如根据若干个url异步加载多张图片，然后在都下载完成后合成一张整图）

- 使用Dispatch Group追加block到Global Group Queue,这些block如果全部执行完毕，就会执行Main Dispatch Queue中的结束处理的block。

```
dispatch_queue_t queue = dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0);
dispatch_group_t group = dispatch_group_create();
dispatch_group_async(group, queue, ^{ /*加载图片1 */ });
dispatch_group_async(group, queue, ^{ /*加载图片2 */ });
dispatch_group_async(group, queue, ^{ /*加载图片3 */ }); 
dispatch_group_notify(group, dispatch_get_main_queue(), ^{
        // 合并图片
});
```


## 40.dispatch_barrier_async的作用是什么？

- 栅栏函数
- 毫无疑问,dispatch_barrier_async函数的作用与barrier的意思相同,在进程管理中起到一个栅栏的作用,在并行队列中，为了保持某些任务的顺序，需要等待一些任务完成后才能继续进行，使用 barrier 来等待之前任务完成，避免数据竞争等问题。 dispatch_barrier_async 函数会等待追加到Concurrent Dispatch Queue并行队列中的操作全部执行完之后，然后再执行 dispatch_barrier_async 函数追加的处理，等 dispatch_barrier_async 追加的处理执行结束之后，Concurrent Dispatch Queue才恢复之前的动作继续执行。
- 实现高效率的数据库访问和文件访问
- 避免数据竞争

## 41.苹果为什么要废弃dispatch_get_current_queue？

- dispatch_get_current_queue容易造成死锁。
- 在iOS6.0被删除的。
- 造成死锁的原因：
    * 可重入的概念：若一个程序或子程序可以“安全的被并行执行(Parallel computing)”，则称其为可重入（reentrant或re-entrant）的。即当该子程序正在运行时，可以再次进入并执行它。
    * 若一个函数是可重入的，则该函数：
        * 不能含有静态（全局）非常量数据
        * 不能返回静态（全局）非常量数据的地址
        * 只能处理由调用者提供的数据
        * 不能依赖于单实例模式资源的锁
        * 不能调用(call)不可重入的函数(有呼叫(call)到的函数需满足前述条件)
    * 有时候我们很希望知道当前执行的queue是谁，比如UI操作需要放在main queue中执行。如果可以知道当前工作的queue是谁，就可以很方便的指定一段代码操作在特定的queue中执行。 dispatch_get_current_queue() 正好能帮上忙。于是乎，在指定的queue中做一些操作，就可以非常清晰的实现：
    
```
void func(dispatch_queue_t queue, dispatch_block_t block)  
{  
    if (dispatch_get_current_queue() == queue) {  
        block();  
    }else{  
        dispatch_sync(queue, block);  
    }  
} 

```
    
然后潜意识里，觉得这个函数是可重入的。但当target queue恰好是current queue时，同步阻塞会导致死锁。

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
只输出：1 。发生主线程锁死。
- 详解：
    * 因为dispatch_get_main_queue()得到的是一个串行队列，串行队列的特点： 一次只调度一个任务，队列中的任务一个接着一个的执行（一个任务执行完毕后，再执行下一个任务）同步（sync）操作，它会阻塞当前线程并等待Block中的任务执行完毕，然后当前线程才会继续往下运行 dispatch_sync提交一个打印任务NSLog(@”2”)到主线程关联的串行队列中，主线程关联的串行队列现在有一个viewDidLoad任务，打印任务NSLog(@”2”)排在viewDidLoad后面，队列FIFO（先进先出）的原则，打印任务NSLog(@”2”);想要得到执行必须等到viewDidLoad执行完毕后才能得到执行，但是viewDidLoad想要执行完毕必须要等打印任务NSLog(@”2”)执行完毕，所以就卡死在这了。

## 43.addObserver:forKeyPath:options:context:各个参数的作用分别是什么，observer中需要实现哪个方法才能获得KVO回调？

```
// 添加键值观察
/*
1 观察者，负责处理监听事件的对象
2 观察的属性
3 观察的选项
4 上下文
5 self.person 被观察者
6 self        观察者
7 forKeyPath  观察的属性
8 options     观察的选项
*/
[self.person addObserver:self forKeyPath:@"name" options:NSKeyValueObservingOptionNew | NSKeyValueObservingOptionOld context:@"Person Name"];
```
observer中需要实现一下方法：

```
// 所有的 kvo 监听到事件，都会调用此方法
/*
 1. 观察的属性
 2. 观察的对象
 3. change 属性变化字典（新／旧）
 4. 上下文，与监听的时候传递的一致
 */
- (void)observeValueForKeyPath:(NSString *)keyPath ofObject:(id)object change:(NSDictionary *)change context:(void *)context;
```


## 44.如何手动触发一个value的KVO

- 所谓的“手动触发”是区别于“自动触发”：
- 自动触发是指类似这种场景：在注册 KVO 之前设置一个初始值，注册之后，设置一个不一样的值，就可以触发了。
- 想知道如何手动触发，必须知道自动触发 KVO 的原理：
    * 键值观察通知依赖于 NSObject 的两个方法: willChangeValueForKey: 和 didChangevlueForKey: 。在一个被观察属性发生改变之前， willChangeValueForKey: 一定会被调用，这就 会记录旧的值。而当改变发生后， observeValueForKey:ofObject:change:context: 会被调用，继而 didChangeValueForKey: 也会被调用。如果可以手动实现这些调用，就可以实现“手动触发”了。
    * 那么“手动触发”的使用场景是什么？一般我们只在希望能控制“回调的调用时机”时才会这么做。
具体做法如下：

如果这个 value 是 表示时间的 self.now ，那么代码如下：最后两行代码缺一不可。

```
//  .m文件
//  手动触发 value 的KVO，最后两行代码缺一不可。

//@property (nonatomic, strong) NSDate *now;
- (void)viewDidLoad {
   [super viewDidLoad];
   _now = [NSDate date];
   [self addObserver:self forKeyPath:@"now" options:NSKeyValueObservingOptionNew context:nil];
   NSLog(@"1");
   [self willChangeValueForKey:@"now"]; // “手动触发self.now的KVO”，必写。
   NSLog(@"2");
   [self didChangeValueForKey:@"now"]; // “手动触发self.now的KVO”，必写。
   NSLog(@"4");
}
```
但是平时我们一般不会这么干，我们都是等系统去“自动触发”。“自动触发”的实现原理：
> 比如调用 setNow: 时，系统还会以某种方式在中间插入 wilChangeValueForKey: 、 didChangeValueForKey: 和 observeValueForKeyPath:ofObject:change:context: 的调用。

大家可能以为这是因为 setNow: 是合成方法，有时候我们也能看到有人这么写代码:

```
- (void)setNow:(NSDate *)aDate {
   [self willChangeValueForKey:@"now"]; // 没有必要
   _now = aDate;
   [self didChangeValueForKey:@"now"];// 没有必要
}
```
这完全没有必要，不要这么做，这样的话，KVO代码会被调用两次。KVO在调用存取方法之前总是调用 willChangeValueForKey: ，之后总是调用 didChangeValueForkey: 。


## 45.若一个类有实例变量 NSString *_foo ，调用setValue:forKey:时，可以以foo还是 _foo 作为key？

- 都可以。

## 46.KVC的keyPath中的集合运算符如何使用？

- 必须用在集合对象上或普通对象的集合属性上
- 简单集合运算符有@avg， @count ， @max ， @min ，@sum，
- 格式 @"@sum.age"或 @"集合属性.@max.age"
- 例子：
首先造一些测试数据、后面使用

```
- (NSArray *) loadData
{
    //假数据
    Student *stu0 = [[Student alloc]init];
    stu0.stuId = 0;
    stu0.name = @"tom";
    stu0.score = 88;
    
    Student *stu1 = [[Student alloc]init];
    stu1.stuId = 1;
    stu1.name = @"sam";
    stu1.score = 90;
    
    Student *stu2 = [[Student alloc]init];
    stu2.stuId = 2;
    stu2.name = @"xiaoming";
    stu2.score = 65;
    
    Student *stu3 = [[Student alloc]init];
    stu3.stuId = 3;
    stu3.name = @"shangsan";
    stu3.score = 89;
    
    //此学生和stu3同名
    Student *stu4 = [[Student alloc]init];
    stu4.stuId = 4;
    stu4.name = @"shangsan";
    stu4.score = 91;
    
    return @[stu0,stu1,stu2,stu3,stu4];
}```

#####简单集合操作符
>   `@count`: 返回一个值为集合中对象总数的NSNumber对象。
      `@sum`:   首先把集合中的每个对象都转换为double类型，然后计算其总，最后返回一个值为这个总和的NSNumber对象。
      `@avg`:   首先把集合中的每个对象都转换为double类型，然后计算其均分，最后返回一个值为这个总和的NSNumber对象。
      `@max`:   使用compare:方法来确定最大值。所以为了让其正常工作，集合中所有的对象都必须支持和另一个对象的比较。
      `@min`:   和@max一样，但是返回的是集合中的最小值。

```
//获取学生数据
NSArray *arr = [self loadData];

```
/**
 简单集合操作符
  @count: 返回一个值为集合中对象总数的NSNumber对象。
  @sum:   首先把集合中的每个对象都转换为double类型，然后计算其总，最后返回一个值为这个总和的NSNumber对象。
  @avg:   首先把集合中的每个对象都转换为double类型，然后计算其均分，最后返回一个值为这个总和的NSNumber对象。
  @max:   使用compare:方法来确定最大值。所以为了让其正常工作，集合中所有的对象都必须支持和另一个对象的比较。
  @min:   和@max一样，但是返回的是集合中的最小值。
 */

//注：--->   @
//KVC集合运算符允许在valueForKeyPath:方法中使用key path符号在一个集合中执行方法。无论什么时候你在key path中看见了@，它都代表了一个特定的集合方法，其结果可以被返回或者链接，就像其他的key path一样。

NSLog(@"学生集合平均分 = %@",[arr valueForKeyPath:@"@avg.score"]);
NSLog(@"学生集合总数  = %@",[arr valueForKeyPath:@"@count"]);
NSLog(@"学生集合最该分 = %@",[arr valueForKeyPath:@"@max.score"]);
NSLog(@"学生集合最低分 = %@",[arr valueForKeyPath:@"@min.score"]);
NSLog(@"学生集合成绩总和 = %@",[arr valueForKeyPath:@"@sum.score"]);

```

```
打印结果：
![简单集合操作符](http://upload-images.jianshu.io/upload_images/1599305-2543477be98d8c10.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



#####对象操作符
> `@unionOfObjects`/ `@distinctUnionOfObjects`: 返回一个由操作符右边的key path所指定的对象属性组成的数组。
       其中:
        `@distinctUnionOfObjects` 会对数组去重, 
        `@unionOfObjects` 不会对数组去重

```

```
/**
   对象操作符
 
   @unionOfObjects / @distinctUnionOfObjects: 返回一个由操作符右边的key path所指定的对象属性组成的数组。
   其中:
    @distinctUnionOfObjects 会对数组去重, 
    @unionOfObjects 不会对数组去重
 */
NSLog(@"%@",[arr valueForKeyPath:@"@unionOfObjects.name"]);
NSLog(@"%@",[arr valueForKeyPath:@"@distinctUnionOfObjects.name"]);

```

```
打印结果：
![对象操作符](http://upload-images.jianshu.io/upload_images/1599305-5063d87616d26289.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#####数组和集合操作符
>    `@distinctUnionOfArrays` / `@unionOfArrays`: 返回了一个数组，其中包含这个集合中每个数组对于这个操作符右面指定的key path进行操作之后的值。正如你期望的，distinct版本会移除重复的值。
     `@distinctUnionOfSets`: 和`@distinctUnionOfArrays`差不多, 但是它期望的是一个包含着NSSet对象的NSSet，并且会返回一个NSSet对象。因为集合不能包含重复的值，所以它只有distinct操作。

```

```
/**
  数组和集合操作符
 
 @distinctUnionOfArrays / @unionOfArrays: 返回了一个数组，其中包含这个集合中每个数组对于这个操作符右面指定的key path进行操作之后的值。正如你期望的，distinct版本会移除重复的值。
 
 @distinctUnionOfSets: 和@distinctUnionOfArrays差不多, 但是它期望的是一个包含着NSSet对象的NSSet，并且会返回一个NSSet对象。因为集合不能包含重复的值，所以它只有distinct操作。
 */

NSArray *arr2 = [self loadData];
NSLog(@"%@",[@[arr,arr2] valueForKeyPath:@"@unionOfArrays.name"]);

```


打印结果：

![数组和集合操作符]

![image](http://upload-images.jianshu.io/upload_images/1599305-6a75ebddd2c1b221.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


## 47.KVC和KVO的keyPath一定是属性么？


## 48.如何关闭默认的KVO的默认实现，并进入自定义的KVO实现？

## 49.apple用什么方式实现对一个对象的KVO？

- 在iOS开发中，苹果提供了许多机制给我们进行回调。KVO(key-value-observing)是一种十分有趣的回调机制，在某个对象注册监听者后，在被监听的对象发生改变时，对象会发送一个通知给监听者，以便监听者执行回调操作。最常见的KVO运用是监听scrollView的contentOffset属性，来完成用户滚动时动态改变某些控件的属性实现效果，包括渐变导航栏、下拉刷新控件等效果。
- Apple 的文档对 KVO 实现的描述：
> Automatic key-value observing is implemented using a technique called isa-swizzling... When an observer is registered for an attribute of an object the isa pointer of the observed object is modified, pointing to an intermediate class rather than at the true class ...
- 从Apple 的文档可以看出：Apple 并不希望过多暴露 KVO 的实现细节。不过，要是借助 runtime 提供的方法去深入挖掘，所有被掩盖的细节都会原形毕露：
> 当你观察一个对象时，一个新的类会被动态创建。这个类继承自该对象的原本的类，并重写了被观察属性的 setter 方法。重写的 setter 方法会负责在调用原 setter 方法之前和之后，通知所有观察对象：值的更改。最后通过 isa 混写（isa-swizzling） 把这个对象的 isa 指针 ( isa 指针告诉 Runtime 系统这个对象的类是什么 )（关于更多isa指针，点击[这里](https://note.youdao.com/)） 指向这个新创建的子类，对象就神奇的变成了新创建的子类的实例。
如下图

![image](https://camo.githubusercontent.com/9517b0d78961b5f32cf3392b99964f2e1f79fb35/687474703a2f2f6936322e74696e797069632e636f6d2f7379353775722e6a7067)

KVO 确实有点黑魔法：
> Apple 使用了 isa 混写（isa-swizzling）来实现 KVO 。

- 下面做下详细解释：

键值观察通知依赖于 NSObject 的两个方法: willChangeValueForKey: 和 didChangevlueForKey: 。在一个被观察属性发生改变之前， willChangeValueForKey: 一定会被调用，这就会记录旧的值。而当改变发生后， observeValueForKey:ofObject:change:context: 会被调用，继而 didChangeValueForKey: 也会被调用。可以手动实现这些调用，但很少有人这么做。一般我们只在希望能控制回调的调用时机时才会这么做。大部分情况下，改变通知会自动调用。

比如调用 setNow: 时，系统还会以某种方式在中间插入 wilChangeValueForKey: 、 didChangeValueForKey: 和 observeValueForKeyPath:ofObject:change:context: 的调用。大家可能以为这是因为 setNow: 是合成方法，有时候我们也能看到有人这么写代码:
 
```
- (void)setNow:(NSDate *)aDate {
   [self willChangeValueForKey:@"now"]; // 没有必要
   _now = aDate;
   [self didChangeValueForKey:@"now"];// 没有必要
}
```
这完全没有必要，不要这么做，这样的话，KVO代码会被调用两次。KVO在调用存取方法之前总是调用 willChangeValueForKey: ，之后总是调用 didChangeValueForkey: 。怎么做到的呢?答案是通过 isa 混写（isa-swizzling）。第一次对一个对象调用 addObserver:forKeyPath:options:context: 时，框架会创建这个类的新的 KVO 子类，并将被观察对象转换为新子类的对象。在这个 KVO 特殊子类中， Cocoa 创建观察属性的 setter ，大致工作原理如下:

```
- (void)setNow:(NSDate *)aDate {
   [self willChangeValueForKey:@"now"];
   [super setValue:aDate forKey:@"now"];
   [self didChangeValueForKey:@"now"];
}
```
这种继承和方法注入是在运行时而不是编译时实现的。这就是正确命名如此重要的原因。只有在使用KVC命名约定时，KVO才能做到这一点。

KVO 在实现中通过 isa 混写（isa-swizzling） 把这个对象的 isa 指针 ( isa 指针告诉 Runtime 系统这个对象的类是什么 ) 指向这个新创建的子类，对象就神奇的变成了新创建的子类的实例。这在Apple 的文档可以得到印证：
> Automatic key-value observing is implemented using a technique called isa-swizzling... When an observer is registered for an attribute of an object the isa pointer of the observed object is modified, pointing to an intermediate class rather than at the true class ...

然而 KVO 在实现中使用了 isa 混写（ isa-swizzling） ，这个的确不是很容易发现：Apple 还重写、覆盖了 -class 方法并返回原来的类。 企图欺骗我们：这个类没有变，就是原本那个类。。。

但是，假设“被监听的对象”的类对象是 MYClass ，有时候我们能看到对 NSKVONotifying_MYClass 的引用而不是对 MYClass 的引用。借此我们得以知道 Apple 使用了 isa 混写（isa-swizzling）。具体探究过程可参考 这篇博文 。

那么 wilChangeValueForKey: 、 didChangeValueForKey: 和 observeValueForKeyPath:ofObject:change:context: 这三个方法的执行顺序是怎样的呢？

wilChangeValueForKey: 、 didChangeValueForKey: 很好理解，observeValueForKeyPath:ofObject:change:context: 的执行时机是什么时候呢？

先看一个例子：

```
- (void)viewDidLoad {
   [super viewDidLoad];
   [self addObserver:self forKeyPath:@"now" options:NSKeyValueObservingOptionNew context:nil];
   NSLog(@"1");
   [self willChangeValueForKey:@"now"]; // “手动触发self.now的KVO”，必写。
   NSLog(@"2");
   [self didChangeValueForKey:@"now"]; // “手动触发self.now的KVO”，必写。
   NSLog(@"4");
}

- (void)observeValueForKeyPath:(NSString *)keyPath ofObject:(id)object change:(NSDictionary<NSString *,id> *)change context:(void *)context {
   NSLog(@"3");
}
```

![image](https://camo.githubusercontent.com/154f30ca6e4fbb77af74b8186057b7f7c96221ff/687474703a2f2f6936362e74696e797069632e636f6d2f6e636d3774682e6a7067)
   
如果单单从下面这个例子的打印上，顺序似乎是 wilChangeValueForKey: 、 observeValueForKeyPath:ofObject:change:context: 、 didChangeValueForKey: 。
其实不然，这里有一个 observeValueForKeyPath:ofObject:change:context: , 和 didChangeValueForKey: 到底谁先调用的问题：如果 observeValueForKeyPath:ofObject:change:context: 是在 didChangeValueForKey: 内部触发的操作呢？ 那么顺序就是： wilChangeValueForKey: 、 didChangeValueForKey: 和 observeValueForKeyPath:ofObject:change:context:

不信你把 didChangeValueForKey: 注视掉，看下 observeValueForKeyPath:ofObject:change:context: 会不会执行。

了解到这一点很重要，正如“手动触发”的使用场景是什么？一般我们只在希望能控制“回调的调用时机”时才会这么做。而“回调的调用时机”就是在你调用 didChangeValueForKey: 方法时。


## 50.IBOutlet连出来的视图属性为什么可以被设置成weak?

- 官方文档里面说：一般的IBOutlet直接关联到viewcontroller。但是跟其关联的控件并不是添加在controller上，而是添加到controller的view上，比如[self.view addSubView：xxx]; 这个时候self.view已经对xxx 强引用过了，self.view才是持有xxx的对象。这样子才符合引用计数的规则。所以直接IBOutlet顶级view的时候肯定是strong的。
- 其实质是：使用storyboard创建的viewController，那么会有一个叫 _topLevelObjectsToKeepAliveFromStoryboard的私有数组强引用所有top level的对象，同时top level对象强引用所有子对象，那么vc没必要再强引用top level对象的子对象。
- 以UIButton为例：UIViewController->UIView->UIButton
    * 如果我们在vc中这样写

```
@IBOutlet weak var bu: UIButton!
```
他们之间的引用关系用图表示如下：

![image](http://jbcdn2.b0.upaiyun.com/2016/03/5f5fef26ea7d3eb2dd997e21d1254758.png)
viewController强引用view对象，同时view强引用button对象，那么你声明属性的时候使用weak就可以了。（觉得Strong也可以，但是完全没必要）

释放过程：其实不管声明的属性是强引用还是弱引用，在控制器消失的时候，这个属性消失，View消失，subViews消失，控件也就消失了。


## 51.IB中User Defined Runtime Attributes如何使用？

- 用户定义的运行时属性
- 它能够通过KVC的方式配置一些你在interface builder 中不能配置的属性。当你希望在IB中作尽可能多得事情，这个特性能够帮助你编写更加轻量级的viewcontroller
- 当你使用IB（Storyboard或者Xib）编辑视图的时候，有时可能会遇到诸如 圆角、边框、边框颜色、控件背景颜色等等难以通过IB直接设置的属性。这时你不得不借助代码实现。其实当出现这类情况时,我们其实可以借助Runtime Attribute在IB中实现。
- 在IB中，点击任意一个控件切换到identity inspector

![image](https://upload-images.jianshu.io/upload_images/2791656-10f9e2c59df07f7b.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/300)
- 属性类型
    * 下面是一些可用的Attribute Types与其相对应的数据类型:
        * Boolean – BOOL
        * Number – NSNumber * 
        * String – NSString *
        * Point – CGPoint
        * Size – CGSize
        * Rect – CGRect
        * Range – NSRange
        * Color – UIColor *
        * Image - UIImage imageNamed
    
==注意：在user defined runtime attributes（用户定义的运行时属性）是没有报错机制的，我们必须保障每一个属性都要写正确（尤其是大小写）和每个Type的数据类型选择正确==

## 52.如何调试BAD_ACCESS错误

- BAD_ACCESS错误在什么情况下出现
    * BAD_ACCESS 报错属于内存访问错误，会导致程序崩溃，错误的原因是访问了野指针(悬挂指针)。野指针指的是本来指针指向的对象已经释放了，但指向该对象的指针没有置 nil，指针指向随机的未知的内存，程序还以为该指针指向那个对象，导致存在一些潜在的危险访问操作，这些危险访问操作无法被指针指向的未知内存所处理，就会导致BAD_ACCESS错误造成程序崩溃。访问的含义包括多种情况，例如:向野指针发送消息，读写野指针本来指向的对象的成员变量等等。
- 如何调试 BAD_ACCESS 错误
    * 我们知道BAD_ACCESS错误是由于访问了野指针，但程序不会在野指针出现时或者在我们访问野指针的代码处报错，导致对其难以察觉，
    * 开启僵尸对象，通过 zombie objects，选择工具条中的Product-> 选择 Scheme -> 选择 Edit Scheme，选择左侧的Run，打开顶部标签中的Diagnotics(诊断)，勾选复选框Enable Zombie Objects。![image](http://7xlt6k.com1.z0.glb.clouddn.com/屏幕快照%202015-11-01%2019.05.57.png)
        * 在Xcode中，你可以启用僵尸对象（zombie objects），这意味着，被释放的对象作为『僵尸』来被保持。换句话说，被释放的对象为了调试程序而被保持活跃。这没有什么神奇的作用。如果你将消息发送给一个僵尸对象，你的应用程序仍然会得到一个EXC_BAD_ACCESS的崩溃。
        * 为什么启用zombie是有用的？让EXC_BAD_ACCESS难以调试的原因是：你不知道你的应用程序尝试去访问的对象是什么。在多种情况下，僵尸对象能够解决这个问题。通过使被释放的对象保持活跃，Xcode能够告诉你应用程序试图访问的对象，并使问题的检索更加简单。
    * Analyze静态分析
        * 不幸的是，僵尸对象不能解决你所遇到的任何由EXC_BAD_ACCESS所引起的崩溃。如果僵尸对象不能解决你的问题，那么试着去做一些分析。
        * 选择Product->Analyze，或者快捷方式Shift+Command+B，来启用Xcode对你的项目的分析。
    * 重写object的respondsToSelector方法，现实出现EXEC_BAD_ACCESS前访问的最后一个object。
    * 设置全局断点快速定位问题代码所在行。
    * BAD_ACCESS捕获功能：Address Sanitizer。



## 53. lldb（gdb）常用的调试命令？

- po:打印对象,会调用对象 description 方法。是 print-object 的简写
- expr:可以在调试时动态执行指定表达式,并将结果打印出来,很有用的命令
- print:也是打印命令,需要指定类型
- bt:打印调用堆栈,是 thread backtrace 的简写,加 all 可打印所有thread 的堆栈
- br l:是 breakpoint list 的简写，设置断点定位到某一个函数
- n:是换行
- p:是打印这个对象所属的类,即其父类
- 更多具体命令
    * 苹果官方文档： [iOS Debugging Magic](https://developer.apple.com/library/content/technotes/tn2239/_index.html) 。
