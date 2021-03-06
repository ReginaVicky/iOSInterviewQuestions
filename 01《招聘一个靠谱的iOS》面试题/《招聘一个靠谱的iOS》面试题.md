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

# 在微博@iOS程序犭袁的答案整理中多出来的题整理如下

54. [runtime如何通过selector找到对应的IMP地址？（分别考虑类方法和实例方法）](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#54-runtime如何通过selector找到对应的imp地址分别考虑类方法和实例方法)

55. [使用runtime Associate方法关联的对象，需要在主对象dealloc的时候释放么？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#55-使用runtime-associate方法关联的对象需要在主对象dealloc的时候释放么)

56. [objc中的类方法和实例方法有什么本质区别和联系？](https://github.com/ReginaVicky/iOSInterviewQuestions/blob/master/01《招聘一个靠谱的iOS》面试题/《招聘一个靠谱的iOS》面试题.md#56-objc中的类方法和实例方法有什么本质区别和联系)



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
1. enum 建议使用 NS_ENUM 和 NS_OPTIONS 宏来定义枚举类型

```
//定义一个枚举
   typedef NS_ENUM(NSInteger, CYLSex) {
       CYLSexMan,
       CYLSexWoman
   };
```
（仅仅让性别包含男和女可能并不严谨）
2. age 属性的类型：应避免使用基本类型，建议使用 Foundation 数据类型，对应关系如下：

```
    int -> NSInteger
    unsigned -> NSUInteger
    float -> CGFloat
    动画时间 -> NSTimeInterval
```
同时考虑到 age 的特点，应使用 NSUInteger ，而非 int 。
3. 如果工程项目非常庞大，需要拆分成不同的模块，可以在类、typedef宏命名的时候使用前缀。
4. doLogIn方法不应写在该类中：无论是 MVC 模式还是 MVVM 模式，业务逻辑都不应当写在 Model 里：MVC 应在 C，MVVM 应在 VM。
5. doLogIn 方法命名不规范：添加了多余的动词前缀。 请牢记：如果方法表示让对象执行一个动作，使用动词打头来命名，注意不要使用 do，does 这种多余的关键字，动词本身的暗示就足够了。应为 -logIn 
6. -(id)initUserModelWithUserName: (NSString*)name withAge:(int)age;方法中不要用 with 来连接两个参数: withAge: 应当换为age:，age: 已经足以清晰说明参数的作用，也不建议用 andAge: ：通常情况下，即使有类似 withA:withB: 的命名需求，也通常是使用withA:andB: 这种命名，用来表示方法执行了两个相对独立的操作（从设计上来说，这时候也可以拆分成两个独立的方法），它不应该用作阐明有多个参数，比如下面的：

```
//错误，不要使用"and"来连接参数
- (int)runModalForDirectory:(NSString *)path andFile:(NSString *)name andTypes:(NSArray *)fileTypes;
//错误，不要使用"and"来阐明有多个参数
- (instancetype)initWithName:(CGFloat)width andAge:(CGFloat)height;
//正确，使用"and"来表示两个相对独立的操作
- (BOOL)openFile:(NSString *)fullPath withApplication:(NSString *)appName andDeactivate:(BOOL)flag;
```
7. 由于字符串值可能会改变，所以要把相关属性的“内存管理语义”声明为 copy 。
8. “性别”(sex）属性的：该类中只给出了一种“初始化方法” (initializer)用于设置“姓名”(Name)和“年龄”(Age)的初始值，那如何对“性别”(Sex）初始化？

Objective-C 有 designated 和 secondary 初始化方法的观念。 designated 初始化方法是提供所有的参数，secondary 初始化方法是一个或多个，并且提供一个或者更多的默认参数来调用 designated 初始化方法的初始化方法。举例说明：

```
// .m文件
   //

   @implementation CYLUser

   - (instancetype)initWithName:(NSString *)name
                            age:(NSUInteger)age
                            sex:(CYLSex)sex {
       if(self = [super init]) {
           _name = [name copy];
           _age = age;
           _sex = sex;
       }
       return self;
   }

   - (instancetype)initWithName:(NSString *)name
                            age:(NSUInteger)age {
       return [self initWithName:name age:age sex:nil];
   }

   @end
```
上面的代码中initWithName:age:sex: 就是 designated 初始化方法，另外的是 secondary 初始化方法。因为仅仅是调用类实现的 designated 初始化方法。

因为出题者没有给出 .m 文件，所以有两种猜测：1：本来打算只设计一个 designated 初始化方法，但漏掉了“性别”(sex）属性。那么最终的修改代码就是上文给出的第一种修改方法。2：不打算初始时初始化“性别”(sex）属性，打算后期再修改，如果是这种情况，那么应该把“性别”(sex）属性设为 readwrite 属性，最终给出的修改代码应该是：

```
// .h文件
 
   // 第二种修改方法（基于第一种修改方法的基础上）

   typedef NS_ENUM(NSInteger, CYLSex) {
       CYLSexMan,
       CYLSexWoman
   };

   @interface CYLUser : NSObject<NSCopying>

   @property (nonatomic, readonly, copy) NSString *name;
   @property (nonatomic, readonly, assign) NSUInteger age;
   @property (nonatomic, readwrite, assign) CYLSex sex;

   - (instancetype)initWithName:(NSString *)name age:(NSUInteger)age sex:(CYLSex)sex;
   - (instancetype)initWithName:(NSString *)name age:(NSUInteger)age;
   + (instancetype)userWithName:(NSString *)name age:(NSUInteger)age sex:(CYLSex)sex;

   @end
```
.h 中暴露 designated 初始化方法，是为了方便子类化

- 按照接口设计的惯例，如果设计了“初始化方法” (initializer)，也应当搭配一个快捷构造方法。而快捷构造方法的返回值，建议为 instancetype，为保持一致性，init 方法和快捷构造方法的返回类型最好都用 instancetype。
- 如果基于第一种修改方法：既然该类中已经有一个“初始化方法” (initializer)，用于设置“姓名”(Name)、“年龄”(Age)和“性别”(Sex）的初始值: 那么在设计对应 @property 时就应该尽量使用不可变的对象：其三个属性都应该设为“只读”。用初始化方法设置好属性值之后，就不能再改变了。在本例中，仍需声明属性的“内存管理语义”。于是可以把属性的定义改成这样

```
@property (nonatomic, readonly, copy) NSString *name;
       @property (nonatomic, readonly, assign) NSUInteger age;
       @property (nonatomic, readonly, assign) CYLSex sex;
```
由于是只读属性，所以编译器不会为其创建对应的“设置方法”，即便如此，我们还是要写上这些属性的语义，以此表明初始化方法在设置这些属性值时所用的方式。要是不写明语义的话，该类的调用者就不知道初始化方法里会拷贝这些属性，他们有可能会在调用初始化方法之前自行拷贝属性值。这种操作多余而且低效。

9. initUserModelWithUserName 如果改为 initWithName 会更加简洁，而且足够清晰。
10. UserModel 如果改为 User 会更加简洁，而且足够清晰。
11. UserSex如果改为Sex 会更加简洁，而且足够清晰。
12. 第二个 @property 中 assign 和 nonatomic 调换位置。 推荐按照下面的格式来定义属性

```
@property (nonatomic, readwrite, copy) NSString *name;
```



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

- 用途：
    * NSString、NSArray、NSDictionary 等等经常使用copy关键字，是因为他们有对应的可变类型：NSMutableString、NSMutableArray、NSMutableDictionary；
    * block 也经常使用 copy 关键字，具体原因见官方文档：Objects Use Properties to Keep Track of Blocks：
- block 使用 copy 是从 MRC 遗留下来的“传统”,在 MRC 中,方法内部的 block 是在栈区的,使用 copy 可以把它放到堆区.在 ARC 中写不写都行：对于 block 使用 copy 还是 strong 效果是一样的，但写上 copy 也无伤大雅，还能时刻提醒我们：编译器自动对 block 进行了 copy 操作。如果不写 copy ，该类的调用者有可能会忘记或者根本不知道“编译器会自动对 block 进行了 copy 操作”，他们有可能会在调用之前自行拷贝属性值。这种操作多余而低效。你也许会感觉我这种做法有些怪异，不需要写依然写。如果你这样想，其实是你“日用而不知”，你平时开发中是经常在用我说的这种做法的，比如下面的属性不写copy也行，但是你会选择写还是不写呢？

```
@property (nonatomic, copy) NSString *userId;

- (instancetype)initWithUserId:(NSString *)userId {
   self = [super init];
   if (!self) {
       return nil;
   }
   _userId = [userId copy];
   return self;
}
```

![image](https://camo.githubusercontent.com/8a5fa34435801cc4c2715d8880f3abd45be6a6c5/687474703a2f2f692e696d6775722e636f6d2f566c564b6c384c2e706e67)

下面做下解释： copy 此特质所表达的所属关系与 strong 类似。然而设置方法并不保留新值，而是将其“拷贝” (copy)。 当属性类型为 NSString 时，经常用此特质来保护其封装性，因为传递给设置方法的新值有可能指向一个 NSMutableString 类的实例。这个类是 NSString 的子类，表示一种可修改其值的字符串，此时若是不拷贝字符串，那么设置完属性之后，字符串的值就可能会在对象不知情的情况下遭人更改。所以，这时就要拷贝一份“不可变” (immutable)的字符串，确保对象中的字符串值不会无意间变动。只要实现属性所用的对象是“可变的” (mutable)，就应该在设置新属性值时拷贝一份。
> 用 @property 声明 NSString、NSArray、NSDictionary 经常使用 copy 关键字，是因为他们有对应的可变类型：NSMutableString、NSMutableArray、NSMutableDictionary，他们之间可能进行赋值操作，为确保对象中的字符串值不会无意间变动，应该在设置新属性值时拷贝一份。


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
至于***如何重写带 copy 关键字的 setter***这个问题，

如果抛开本例来回答的话，如下：

```
- (void)setName:(NSString *)name {
    //[_name release];
    _name = [name copy];
}
```
不过也有争议，有人说“苹果如果像下面这样干，是不是效率会高一些？”

```
- (void)setName:(NSString *)name {
   if (_name != name) {
       //[_name release];//MRC
       _name = [name copy];
   }
}
```
你可能会说：

之所以在这里做if判断 这个操作：是因为一个 if 可能避免一个耗时的copy，还是很划算的。 (在刚刚讲的：《如何让自己的类用 copy 修饰符？》里的那种复杂的copy，我们可以称之为 “耗时的copy”，但是对 NSString 的 copy 还称不上。)

但是你有没有考虑过代价：

你每次调用 setX: 都会做 if 判断，这会让 setX: 变慢，如果你在 setX:写了一串复杂的 if+elseif+elseif+... 判断，将会更慢。
要回答“哪个效率会高一些？”这个问题，不能脱离实际开发，就算 copy 操作十分耗时，if 判断也不见得一定会更快，除非你把一个“ @property他当前的值 ”赋给了他自己，代码看起来就像：

```
[a setX:x1];
[a setX:x1];    //你确定你要这么干？与其在setter中判断，为什么不把代码写好？
```
或者

```
[a setX:[a x]];   //队友咆哮道：你在干嘛？！！
```
不要在 setter 里进行像 if(_obj != newObj) 这样的判断。

什么情况会在 copy setter 里做 if 判断？ 例如，车速可能就有最高速的限制，车速也不可能出现负值，如果车子的最高速为300，则 setter 的方法就要改写成这样：

```
-(void)setSpeed:(int)_speed{
    if(_speed < 0) speed = 0;
    if(_speed > 300) speed = 300;
    _speed = speed;
}
```
回到这个题目，如果单单就上文的代码而言，我们不需要也不能重写 name 的 setter ：由于是 name 是只读属性，所以编译器不会为其创建对应的“设置方法”，用初始化方法设置好属性值之后，就不能再改变了。（ 在本例中，之所以还要声明属性的“内存管理语义”--copy，是因为：如果不写 copy，该类的调用者就不知道初始化方法里会拷贝这些属性，他们有可能会在调用初始化方法之前自行拷贝属性值。这种操作多余而低效）。

那如何确保 name 被 copy？在初始化方法(initializer)中做：

```
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
```

## 7.@property 的本质是什么？ivar、getter、setter 是如何生成并添加到这个类中的

- @property 的本质是什么？
    * @property = ivar + getter + setter;
- 下面解释下：
    * “属性” (property)有两大概念：ivar（实例变量）、存取方法（access method ＝ getter + setter）。
    * “属性” (property)作为 Objective-C 的一项特性，主要的作用就在于封装对象中的数据。 Objective-C 对象通常会把其所需要的数据保存为各种实例变量。实例变量一般通过“存取方法”(access method)来访问。其中，“获取方法” (getter)用于读取变量值，而“设置方法” (setter)用于写入变量值。这个概念已经定型，并且经由“属性”这一特性而成为 Objective-C 2.0 的一部分。 而在正规的 Objective-C 编码风格中，存取方法有着严格的命名规范。 正因为有了这种严格的命名规范，所以 Objective-C 这门语言才能根据名称自动创建出存取方法。其实也可以把属性当做一种关键字，其表示:
    * 编译器会自动写出一套存取方法，用以访问给定类型中具有给定名称的变量。 所以你也可以这么说：
    * @property = getter + setter;
    * 例如下面这个类：

```
@interface Person : NSObject
@property NSString *firstName;
@property NSString *lastName;
@end
```
上述代码写出来的类与下面这种写法等效：

```
@interface Person : NSObject
- (NSString *)firstName;
- (void)setFirstName:(NSString *)firstName;
- (NSString *)lastName;
- (void)setLastName:(NSString *)lastName;
@end
```
property在runtime中是objc_property_t定义如下:

```
typedef struct objc_property *objc_property_t;
```
而objc_property是一个结构体，包括name和attributes，定义如下：

```
struct property_t {
    const char *name;
    const char *attributes;
};
```
而attributes本质是objc_property_attribute_t，定义了property的一些属性，定义如下：

```
/// Defines a property attribute
typedef struct {
    const char *name;           /**< The name of the attribute */
    const char *value;          /**< The value of the attribute (usually empty) */
} objc_property_attribute_t;
```
而attributes的具体内容是什么呢？其实，包括：类型，原子性，内存语义和对应的实例变量。

例如：我们定义一个string的property@property (nonatomic, copy) NSString *string;，通过 property_getAttributes(property)获取到attributes并打印出来之后的结果为T@"NSString",C,N,V_string

其中T就代表类型，C就代表Copy，N代表nonatomic，V就代表对于的实例变量。

- ivar、getter、setter 是如何生成并添加到这个类中的?
    * “自动合成”( autosynthesis)
完成属性定义后，编译器会自动编写访问这些属性所需的方法，此过程叫做“自动合成”(autosynthesis)。需要强调的是，这个过程由编译 器在编译期执行，所以编辑器里看不到这些“合成方法”(synthesized method)的源代码。除了生成方法代码 getter、setter 之外，编译器还要自动向类中添加适当类型的实例变量，并且在属性名前面加下划线，以此作为实例变量的名字。在前例中，会生成两个实例变量，其名称分别为 _firstName 与 _lastName。也可以在类的实现代码里通过 @synthesize 语法来指定实例变量的名字.

```
@implementation Person
@synthesize firstName = _myFirstName;
@synthesize lastName = _myLastName;
@end
```
我为了搞清属性是怎么实现的,曾经反编译过相关的代码,他大致生成了五个东西
- OBJC_IVAR_$类名$属性名称 ：该属性的“偏移量” (offset)，这个偏移量是“硬编码” (hardcode)，表示该变量距离存放对象的内存区域的起始地址有多远。
- setter 与 getter 方法对应的实现函数
- ivar_list ：成员变量列表
- method_list ：方法列表
- prop_list ：属性列表

也就是说我们每次在增加一个属性,系统都会在 ivar_list 中添加一个成员变量的描述,在 method_list 中增加 setter 与 getter 方法的描述,在属性列表中增加一个属性的描述,然后计算该属性在对象中的偏移量,然后给出 setter 与 getter 方法对应的实现,在 setter 方法中从偏移量的位置开始赋值,在 getter 方法中从偏移量开始取值,为了能够读取正确字节数,系统对象偏移量的指针类型进行了类型强转.


## 8.@protocol 和 category 中如何使用 @property

- category和protocol都可以添加方法，也都可以添加@property 关键字

- 在 protocol 中使用 property 只会生成 setter 和 getter 方法声明,我们使用属性的目的,是希望遵守我协议的对象能实现该属性，也就是说，在实现这个protocol协议的类中，我们要自己手动添加实例变量，并且需要实现setter和getter方法

- category 使用 @property 也是只会生成 setter 和 getter 方法的声明,由于category不能添加实例变量，故必须通过运行时添加associated object的方法来添加实例变量，如果我们真的需要给 category 增加属性的实现,需要借助于运行时的两个函数：

    * objc_setAssociatedObject

    * objc_getAssociatedObject

## 9.runtime 如何实现 weak 属性

- 要实现 weak 属性，首先要搞清楚 weak 属性的特点：
    * weak 此特质表明该属性定义了一种“非拥有关系” (nonowning relationship)。为这种属性设置新值时，设置方法既不保留新值，也不释放旧值。此特质同 assign 类似， 然而在属性所指的对象遭到摧毁时，属性值也会清空(nil out)。
- 那么 runtime 如何实现 weak 变量的自动置nil？
    * runtime 对注册的类， 会进行布局，对于 weak 对象会放入一个 hash 表中。 用 weak 指向的对象内存地址作为 key，当此对象的引用计数为0的时候会 dealloc，假如 weak 指向的对象内存地址是a，那么就会以a为键， 在这个 weak 表中搜索，找到所有以a为键的 weak 对象，从而设置为 nil。
- 对象的内存销毁时间表，分四个步骤：

```
// 对象的内存销毁时间表
// http://weibo.com/luohanchenyilong/ (微博@iOS程序犭袁)
// https://github.com/ChenYilong
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
- 先看下 runtime 里源码的实现：

```
/**
* The internal structure stored in the weak references table. 
* It maintains and stores
* a hash set of weak references pointing to an object.
* If out_of_line==0, the set is instead a small inline array.
*/
#define WEAK_INLINE_COUNT 4
struct weak_entry_t {
   DisguisedPtr<objc_object> referent;
   union {
       struct {
           weak_referrer_t *referrers;
           uintptr_t        out_of_line : 1;
           uintptr_t        num_refs : PTR_MINUS_1;
           uintptr_t        mask;
           uintptr_t        max_hash_displacement;
       };
       struct {
           // out_of_line=0 is LSB of one of these (don't care which)
           weak_referrer_t  inline_referrers[WEAK_INLINE_COUNT];
       };
   };
};

/**
* The global weak references table. Stores object ids as keys,
* and weak_entry_t structs as their values.
*/
struct weak_table_t {
   weak_entry_t *weak_entries;
   size_t    num_entries;
   uintptr_t mask;
   uintptr_t max_hash_displacement;
};
```
具体完整实现参照 [objc/objc-weak.h](https://opensource.apple.com/source/objc4/objc4-646/runtime/objc-weak.h) 。

- 我们可以设计一个函数（伪代码）来表示上述机制：
    * objc_storeWeak(&a, b)函数：
        * objc_storeWeak函数把第二个参数--赋值对象（b）的内存地址作为键值key，将第一个参数--weak修饰的属性变量（a）的内存地址（&a）作为value，注册到 weak 表中。如果第二个参数（b）为0（nil），那么把变量（a）的内存地址（&a）从weak表中删除，
        * 你可以把objc_storeWeak(&a, b)理解为：objc_storeWeak(value, key)，并且当key变nil，将value置nil。
        * 在b非nil时，a和b指向同一个内存地址，在b变nil时，a变nil。此时向a发送消息不会崩溃：在Objective-C中向nil发送消息是安全的。
        * 而如果a是由 assign 修饰的，则： 在 b 非 nil 时，a 和 b 指向同一个内存地址，在 b 变 nil 时，a 还是指向该内存地址，变野指针。此时向 a 发送消息极易崩溃。
- 下面我们将基于objc_storeWeak(&a, b)函数，使用伪代码模拟“runtime如何实现weak属性”：

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
objc_storeWeak 函数把第二个参数--赋值对象（obj）的内存地址作为键值，将第一个参数--weak修饰的属性变量（obj1）的内存地址注册到 weak 表中。如果第二个参数（obj）为0（nil），那么把变量（obj1）的地址从 weak 表中删除，在后面的相关一题会详解。

- 使用伪代码是为了方便理解，下面我们“真枪实弹”地实现下：
- 如何让不使用weak修饰的@property，拥有weak的效果。
- 我们从setter方法入手：
    * 注意以下的 cyl_runAtDealloc 方法实现仅仅用于模拟原理，如果想用于项目中，还需要考虑更复杂的场景，想在实际项目使用的话，可以使用我写的一个小库，可以使用 CocoaPods 在项目中使用： CYLDeallocBlockExecutor ）

```
- (void)setObject:(NSObject *)object
{
   objc_setAssociatedObject(self, "object", object, OBJC_ASSOCIATION_ASSIGN);
   [object cyl_runAtDealloc:^{
       _object = nil;
   }];
}
```
- 也就是有两个步骤：
1. 在setter方法中做如下设置：
```
objc_setAssociatedObject(self, "object", object, OBJC_ASSOCIATION_ASSIGN);
```
2. 在属性所指的对象遭到摧毁时，属性值也会清空(nil out)。做到这点，同样要借助 runtime：

```
//要销毁的目标对象
id objectToBeDeallocated;
//可以理解为一个“事件”：当上面的目标对象销毁时，同时要发生的“事件”。
id objectWeWantToBeReleasedWhenThatHappens;
objc_setAssociatedObject(objectToBeDeallocted,
                        someUniqueKey,
                        objectWeWantToBeReleasedWhenThatHappens,
                        OBJC_ASSOCIATION_RETAIN);
```
知道了思路，我们就开始实现 cyl_runAtDealloc 方法，实现过程分两部分：

第一部分：创建一个类，可以理解为一个“事件”：当目标对象销毁时，同时要发生的“事件”。借助 block 执行“事件”。

// .h文件

```
// .h文件
// http://weibo.com/luohanchenyilong/
// https://github.com/ChenYilong
// 这个类，可以理解为一个“事件”：当目标对象销毁时，同时要发生的“事件”。借助block执行“事件”。

typedef void (^voidBlock)(void);

@interface CYLBlockExecutor : NSObject

- (id)initWithBlock:(voidBlock)block;

@end
```
// .m文件

```
// .m文件
// http://weibo.com/luohanchenyilong/
// https://github.com/ChenYilong
// 这个类，可以理解为一个“事件”：当目标对象销毁时，同时要发生的“事件”。借助block执行“事件”。

#import "CYLBlockExecutor.h"

@interface CYLBlockExecutor() {
   voidBlock _block;
}
@implementation CYLBlockExecutor

- (id)initWithBlock:(voidBlock)aBlock
{
   self = [super init];
   
   if (self) {
       _block = [aBlock copy];
   }
   
   return self;
}

- (void)dealloc
{
   _block ? _block() : nil;
}

@end
```
第二部分：核心代码：利用runtime实现cyl_runAtDealloc方法

```
// CYLNSObject+RunAtDealloc.h文件
// http://weibo.com/luohanchenyilong/
// https://github.com/ChenYilong
// 利用runtime实现cyl_runAtDealloc方法

#import "CYLBlockExecutor.h"

const void *runAtDeallocBlockKey = &runAtDeallocBlockKey;

@interface NSObject (CYLRunAtDealloc)

- (void)cyl_runAtDealloc:(voidBlock)block;

@end


// CYLNSObject+RunAtDealloc.m文件
// http://weibo.com/luohanchenyilong/
// https://github.com/ChenYilong
// 利用runtime实现cyl_runAtDealloc方法

#import "CYLNSObject+RunAtDealloc.h"
#import "CYLBlockExecutor.h"

@implementation NSObject (CYLRunAtDealloc)

- (void)cyl_runAtDealloc:(voidBlock)block
{
   if (block) {
       CYLBlockExecutor *executor = [[CYLBlockExecutor alloc] initWithBlock:block];
       
       objc_setAssociatedObject(self,
                                runAtDeallocBlockKey,
                                executor,
                                OBJC_ASSOCIATION_RETAIN);
   }
}

@end
```
使用方法： 导入

```
#import "CYLNSObject+RunAtDealloc.h"
```
然后就可以使用了：

```
NSObject *foo = [[NSObject alloc] init];

[foo cyl_runAtDealloc:^{
   NSLog(@"正在释放foo!");
}];
```

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

- 不需要。
- 在ARC环境无论是强指针还是弱指针都无需在 dealloc 设置为 nil ， ARC 会自动帮我们处理
- 即便是编译器不帮我们做这些，weak也不需要在 dealloc 中置nil：
- 我们模拟下 weak 的 setter 方法，应该如下：

```
- (void)setObject:(NSObject *)object
{
   objc_setAssociatedObject(self, "object", object, OBJC_ASSOCIATION_ASSIGN);
   [object cyl_runAtDealloc:^{
       _object = nil;
   }];
}
```
也即:
在属性所指的对象遭到摧毁时，属性值也会清空(nil out)。


## 12.@synthesize和@dynamic分别有什么作用？

- @property有两个对应的词，一个是 @synthesize，一个是 @dynamic。如果 @synthesize和 @dynamic都没写，那么默认的就是@syntheszie var = _var;
- @synthesize 的语义是如果你没有手动实现 setter 方法和 getter 方法，那么编译器会自动为你加上这两个方法。
- @dynamic 告诉编译器：属性的 setter 与 getter 方法由用户自己实现，不自动生成。（当然对于 readonly 的属性只需提供 getter 即可）。假如一个属性被声明为 @dynamic var，然后你没有提供 @setter方法和 @getter 方法，编译的时候没问题，但是当程序运行到 instance.var = someVar，由于缺 setter 方法会导致程序崩溃；或者当运行到 someVar = var 时，由于缺 getter 方法同样会导致崩溃。编译时没问题，运行时才执行相应的方法，这就是所谓的动态绑定。

## 13.ARC下，不显式指定任何属性关键字时，默认的关键字都有哪些？

- 对应基本数据类型默认关键字是
atomic,readwrite,assign 
- 对于普通的 Objective-C 对象 atomic,readwrite,strong


## 14.用@property声明的NSString（或NSArray，NSDictionary）经常使用copy关键字，为什么？如果改用strong关键字，可能造成什么问题？

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


## 15.@synthesize合成实例变量的规则是什么？假如property名为foo，存在一个名为_foo的实例变量，那么还会自动合成新变量么？

在回答之前先说明下一个概念：

实例变量 = 成员变量 ＝ ivar
这些说法，笔者下文中，可能都会用到，指的是一个东西。

正如 Apple官方文档 You Can Customize Synthesized Instance Variable Names 所说：

![image](https://camo.githubusercontent.com/d562010accc0b123c355d48d56b4eb426b032641/687474703a2f2f692e696d6775722e636f6d2f443664307a474a2e706e67)

如果使用了属性的话，那么编译器就会自动编写访问属性所需的方法，此过程叫做“自动合成”( auto synthesis)。需要强调的是，这个过程由编译器在编译期执行，所以编辑器里看不到这些“合成方法” (synthesized method)的源代码。除了生成方法代码之外，编译器还要自动向类中添加适当类型的实例变量，并且在属性名前面加下划线，以此作为实例变量的名字。

```
@interface CYLPerson : NSObject 
@property NSString *firstName; 
@property NSString *lastName; 
@end
```
在上例中，会生成两个实例变量，其名称分别为 _firstName 与 _lastName。也可以在类的实现代码里通过 @synthesize 语法来指定实例变量的名字:

```
@implementation CYLPerson 
@synthesize firstName = _myFirstName; 
@synthesize lastName = _myLastName; 
@end 
```
上述语法会将生成的实例变量命名为 _myFirstName 与 _myLastName ，而不再使用默认的名字。一般情况下无须修改默认的实例变量名，但是如果你不喜欢以下划线来命名实例变量，那么可以用这个办法将其改为自己想要的名字。笔者还是推荐使用默认的命名方案，因为如果所有人都坚持这套方案，那么写出来的代码大家都能看得懂。

- 总结下 @synthesize 合成实例变量的规则，有以下几点：
    * 如果指定了成员变量的名称,会生成一个指定的名称的成员变量,
    * 如果这个成员已经存在了就不再生成了.
    * 如果是 @synthesize foo;              * 还会生成一个名称为foo的成员变量，也就是说：
        * 如果没有指定成员变量的名称会自动生成一个属性同名的成员变量,
    * 如果是 @synthesize foo = _foo; 就不会生成成员变量了.
假如 property 名为 foo，存在一个名为 _foo 的实例变量，那么还会自动合成新变量么？ 不会。如下图：

![image](https://camo.githubusercontent.com/8e11101c9fe0b3defc7fbd144c0dca9fdf0471d0/687474703a2f2f692e696d6775722e636f6d2f743238676534572e706e67)


## 16.在有了自动合成属性实例变量之后，@synthesize还有哪些使用场景？

- 回答这个问题前，我们要搞清楚一个问题，什么情况下不会autosynthesis（自动合成）？
    * 同时重写了 setter 和 getter 时
    * 重写了只读属性的 getter 时
    * 使用了 @dynamic 时
    * 在 @protocol 中定义的所有属性
    * 在 category 中定义的所有属性
    * 重载的属性
- 当你在子类中重载了父类中的属性，你必须 使用 @synthesize 来手动合成ivar。
- 除了后三条，对其他几个我们可以总结出一个规律：当你想手动管理 @property 的所有内容时，你就会尝试通过实现 @property 的所有“存取方法”（the accessor methods）或者使用 @dynamic 来达到这个目的，这时编译器就会认为你打算手动管理 @property，于是编译器就禁用了 autosynthesis（自动合成）。
- 因为有了 autosynthesis（自动合成），大部分开发者已经习惯不去手动定义ivar，而是依赖于 autosynthesis（自动合成），但是一旦你需要使用ivar，而 autosynthesis（自动合成）又失效了，如果不去手动定义ivar，那么你就得借助 @synthesize 来手动合成 ivar。
- 其实，@synthesize 语法还有一个应用场景，但是不太建议大家使用：
可以在类的实现代码里通过 @synthesize 语法来指定实例变量的名字:

```
@implementation CYLPerson 
@synthesize firstName = _myFirstName; 
@synthesize lastName = _myLastName; 
@end 
```
上述语法会将生成的实例变量命名为 _myFirstName 与 _myLastName，而不再使用默认的名字。一般情况下无须修改默认的实例变量名，但是如果你不喜欢以下划线来命名实例变量，那么可以用这个办法将其改为自己想要的名字。笔者还是推荐使用默认的命名方案，因为如果所有人都坚持这套方案，那么写出来的代码大家都能看得懂。

举例说明：应用场景：

```
//
// .m文件

// 打开第14行和第17行中任意一行，就可编译成功

@import Foundation;

@interface CYLObject : NSObject
@property (nonatomic, copy) NSString *title;
@end

@implementation CYLObject {
   //    NSString *_title;
}

//@synthesize title = _title;

- (instancetype)init
{
   self = [super init];
   if (self) {
       _title = @"微博@iOS程序犭袁";
   }
   return self;
}

- (NSString *)title {
   return _title;
}

- (void)setTitle:(NSString *)title {
   _title = [title copy];
}

@end
```
结果编译器报错：

![image](https://camo.githubusercontent.com/a569a90281598d8cc74156fe5f0e3a6ddbf8fc6b/687474703a2f2f692e696d6775722e636f6d2f6641454748496f2e706e67)

- 当你同时重写了 setter 和 getter 时，系统就不会生成 ivar（实例变量/成员变量）。这时候有两种选择：
    * 要么如第14行：手动创建 ivar
    * 要么如第17行：使用@synthesize foo = _foo; ，关联 @property 与 ivar。


## 17.objc中向一个nil对象发送消息将会发生什么？

- 在 Objective-C 中向 nil 发送消息是完全有效的——只是在运行时不会有任何作用:
- 如果一个方法返回值是一个对象，那么发送给nil的消息将返回0(nil)。例如：

```
Person * motherInlaw = [[aPerson spouse] mother];
```
- 如果 spouse 对象为 nil，那么发送给 nil 的消息 mother 也将返回 nil。 
- 如果方法返回值为指针类型，其指针大小为小于或者等于sizeof(void*)，float，double，long double 或者 long long 的整型标量，发送给 nil 的消息将返回0。 
- 如果方法返回值为结构体,发送给 nil 的消息将返回0。结构体中各个字段的值将都是0。 
- 如果方法的返回值不是上述提到的几种情况，那么发送给 nil 的消息的返回值将是未定义的。

具体原因如下：
> objc是动态语言，每个方法在运行时会被动态转为消息发送，即：objc_msgSend(receiver, selector)。

具体分析：

```
// runtime.h（类在runtime中的定义）

struct objc_class {
  Class isa OBJC_ISA_AVAILABILITY; //isa指针指向Meta Class，因为Objc的类的本身也是一个Object，为了处理这个关系，runtime就创造了Meta Class，当给类发送[NSObject alloc]这样消息时，实际上是把这个消息发给了Class Object
  #if !__OBJC2__
  Class super_class OBJC2_UNAVAILABLE; // 父类
  const char *name OBJC2_UNAVAILABLE; // 类名
  long version OBJC2_UNAVAILABLE; // 类的版本信息，默认为0
  long info OBJC2_UNAVAILABLE; // 类信息，供运行期使用的一些位标识
  long instance_size OBJC2_UNAVAILABLE; // 该类的实例变量大小
  struct objc_ivar_list *ivars OBJC2_UNAVAILABLE; // 该类的成员变量链表
  struct objc_method_list **methodLists OBJC2_UNAVAILABLE; // 方法定义的链表
  struct objc_cache *cache OBJC2_UNAVAILABLE; // 方法缓存，对象接到一个消息会根据isa指针查找消息对象，这时会在method Lists中遍历，如果cache了，常用的方法调用时就能够提高调用的效率。
  struct objc_protocol_list *protocols OBJC2_UNAVAILABLE; // 协议链表
  #endif
  } OBJC2_UNAVAILABLE;
```
objc在向一个对象发送消息时，runtime库会根据对象的isa指针找到该对象实际所属的类，然后在该类中的方法列表以及其父类方法列表中寻找方法运行，然后在发送消息的时候，objc_msgSend方法不会返回值，所谓的返回内容都是具体调用时执行的。 那么，回到本题，如果向一个nil对象发送消息，首先在寻找对象的isa指针时就是0地址返回了，所以不会出现任何错误。


## 18.objc中向一个对象发送消息[obj foo]和objc_msgSend()函数之间有什么关系？

- objc是动态语言，每个方法在运行时会被动态转为消息发送，即：objc_msgSend(receiver, selector)。
- 也就是该方法编译之后就是objc_msgSend()函数调用.
- 我们用 clang 分析下，clang 提供一个命令，可以将Objective-C的源码改写成C++语言，借此可以研究下[obj foo]和objc_msgSend()函数之间有什么关系。

以下面的代码为例，由于 clang 后的代码达到了10万多行，为了便于区分，添加了一个叫 iOSinit 方法，

```
//
//  main.m
//

#import "CYLTest.h"

int main(int argc, char * argv[]) {
    @autoreleasepool {
        CYLTest *test = [[CYLTest alloc] init];
        [test performSelector:(@selector(iOSinit))];
        return 0;
    }
}
```
在终端中输入

```
clang -rewrite-objc main.m
```
就可以生成一个main.cpp的文件，在最低端（10万4千行左右）

![image](https://camo.githubusercontent.com/bf346edc21ab4b3387906602249b357d250ab1c2/687474703a2f2f692e696d6775722e636f6d2f6541483559576e2e706e67)

我们可以看到大概是这样的：

```
((void ()(id, SEL))(void )objc_msgSend)((id)obj, sel_registerName("foo"));
```
也就是说：
- [obj foo];在objc编译时，会被转意为：objc_msgSend(obj, @selector(foo));。


## 19.什么时候会报unrecognized selector的异常？

- 简单来说：
    * 当调用该对象上某个方法,而该对象上没有实现这个方法的时候， 
- 可以通过“消息转发”进行解决。
- 由于，objc是动态语言，每个方法在运行时会被动态转为消息发送，即：objc_msgSend(receiver, selector)。
- objc在向一个对象发送消息时，runtime库会根据对象的isa指针找到该对象实际所属的类，然后在该类中的方法列表以及其父类方法列表中寻找方法运行，如果，在最顶层的父类中依然找不到相应的方法时，程序在运行时会挂掉并抛出异常unrecognized selector sent to XXX 。但是在这之前，objc的运行时会给出三次拯救程序崩溃的机会：
    * Method resolution
        * objc运行时会调用+resolveInstanceMethod:或者 +resolveClassMethod:，让你有机会提供一个函数实现。如果你添加了函数，那运行时系统就会重新启动一次消息发送的过程，否则 ，运行时就会移到下一步，消息转发（Message Forwarding）。
    * Fast forwarding
        * 如果目标对象实现了-forwardingTargetForSelector:，Runtime 这时就会调用这个方法，给你把这个消息转发给其他对象的机会。 只要这个方法返回的不是nil和self，整个消息发送的过程就会被重启，当然发送的对象会变成你返回的那个对象。否则，就会继续Normal Fowarding。 这里叫Fast，只是为了区别下一步的转发机制。因为这一步不会创建任何新的对象，但下一步转发会创建一个NSInvocation对象，所以相对更快点。
    * Normal forwarding
        * 这一步是Runtime最后一次给你挽救的机会。首先它会发送-methodSignatureForSelector:消息获得函数的参数和返回值类型。如果-methodSignatureForSelector:返回nil，Runtime则会发出-doesNotRecognizeSelector:消息，程序这时也就挂掉了。如果返回了一个函数签名，Runtime就会创建一个NSInvocation对象并发送-forwardInvocation:消息给目标对象。


## 20.一个objc对象如何进行内存布局？（考虑有父类的情况）

- 所有父类的成员变量和自己的成员变量都会存放在该对象所对应的存储空间中.
- 每一个对象内部都有一个isa指针,指向他的类对象,类对象中存放着本对象的
    * 对象方法列表（对象能够接收的消息列表，保存在它所对应的类对象中）
    * 成员变量的列表,
    * 属性列表,
- 它内部也有一个isa指针指向元对象(meta class),元对象内部存放的是类方法列表,类对象内部还有一个superclass的指针,指向他的父类对象。

每个 Objective-C 对象都有相同的结构，如下图所示：

![image](https://camo.githubusercontent.com/f446a82030de175ad18c7af85f097e1eea3fe496/687474703a2f2f692e696d6775722e636f6d2f376d4a6c556a312e706e67)

翻译过来!

|  Objective-C 对象的结构图 | 
 ------------- |
 ISA指针 |
 根类的实例变量 |
 倒数第二层父类的实例变量 |
 ... |
 父类的实例变量 |
 类的实例变量 | 

- 根对象就是NSObject，它的superclass指针指向nil
- 类对象既然称为对象，那它也是一个实例。类对象中也有一个isa指针指向它的元类(meta class)，即类对象是元类的实例。元类内部存放的是类方法列表，根元类的isa指针指向自己，superclass指针指向NSObject类。

如图: 

![image](http://hi.csdn.net/attachment/201201/19/0_1326963670oeC1.gif)

## 21.一个objc对象的isa的指针指向什么？有什么作用？

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

都输出 Son

```
NSStringFromClass([self class]) = Son
NSStringFromClass([super class]) = Son
```
这个题目主要是考察关于 Objective-C 中对 self 和 super 的理解。

具体分析：
- 我们都知道：self 是类的隐藏参数，指向当前调用方法的这个类的实例。那 super 呢？
- 很多人会想当然的认为“ super 和 self 类似，应该是指向父类的指针吧！”。这是很普遍的一个误区。其实 super 是一个 Magic Keyword， 它本质是一个编译器标示符，和 self 是指向的同一个消息接受者！他们两个的不同点在于：super 会告诉编译器，调用 class 这个方法时，要去父类的方法，而不是本类里的。
- 上面的例子不管调用[self class]还是[super class]，接受消息的对象都是当前 Son ＊xxx 这个对象。
- 当使用 self 调用方法时，会从当前类的方法列表中开始找，如果没有，就从父类中再找；而当使用 super 时，则从父类的方法列表中开始找。然后调用父类的这个方法。
- 这也就是为什么说“不推荐在 init 方法中使用点语法”，如果想访问实例变量 iVar 应该使用下划线（ _iVar ），而非点语法（ self.iVar ）。
- 点语法（ self.iVar ）的坏处就是子类有可能覆写 setter 。假设 Person 有一个子类叫 ChenPerson，这个子类专门表示那些姓“陈”的人。该子类可能会覆写 lastName 属性所对应的设置方法：

```
//
//  ChenPerson.m
//

#import "ChenPerson.h"

@implementation ChenPerson

@synthesize lastName = _lastName;

- (instancetype)init
{
   self = [super init];
   if (self) {
       NSLog(@"🔴类名与方法名：%s（在第%d行），描述：%@", __PRETTY_FUNCTION__, __LINE__, NSStringFromClass([self class]));
       NSLog(@"🔴类名与方法名：%s（在第%d行），描述：%@", __PRETTY_FUNCTION__, __LINE__, NSStringFromClass([super class]));
   }
   return self;
}

- (void)setLastName:(NSString*)lastName
{
   //设置方法一：如果setter采用是这种方式，就可能引起崩溃
//    if (![lastName isEqualToString:@"陈"])
//    {
//        [NSException raise:NSInvalidArgumentException format:@"姓不是陈"];
//    }
//    _lastName = lastName;
   
   //设置方法二：如果setter采用是这种方式，就可能引起崩溃
   _lastName = @"陈";
   NSLog(@"🔴类名与方法名：%s（在第%d行），描述：%@", __PRETTY_FUNCTION__, __LINE__, @"会调用这个方法,想一下为什么？");

}

@end
```
在基类 Person 的默认初始化方法中，可能会将姓氏设为空字符串。此时若使用点语法（ self.lastName ）也即 setter 设置方法，那么调用将会是子类的设置方法，如果在刚刚的 setter 代码中采用设置方法一，那么就会抛出异常，

为了方便采用打印的方式展示，究竟发生了什么，我们使用设置方法二。

如果基类的代码是这样的：

```
/
//  Person.m
//  nil对象调用点语法

#import "Person.h"

@implementation Person

- (instancetype)init
{
   self = [super init];
   if (self) {
       self.lastName = @"";
       //NSLog(@"🔴类名与方法名：%s（在第%d行），描述：%@", __PRETTY_FUNCTION__, __LINE__, NSStringFromClass([self class]));
       //NSLog(@"🔴类名与方法名：%s（在第%d行），描述：%@", __PRETTY_FUNCTION__, __LINE__, self.lastName);
   }
   return self;
}

- (void)setLastName:(NSString*)lastName
{
   NSLog(@"🔴类名与方法名：%s（在第%d行），描述：%@", __PRETTY_FUNCTION__, __LINE__, @"根本不会调用这个方法");
   _lastName = @"炎黄";
}

@end
```
那么打印结果将会是这样的：

```
🔴类名与方法名：-[ChenPerson setLastName:]（在第36行），描述：会调用这个方法,想一下为什么？
🔴类名与方法名：-[ChenPerson init]（在第19行），描述：ChenPerson
🔴类名与方法名：-[ChenPerson init]（在第20行），描述：ChenPerson
```
- 接下来让我们利用 runtime 的相关知识来验证一下 super 关键字的本质，使用clang重写命令:

```
$ clang -rewrite-objc test.m
```
将这道题目中给出的代码被转化为:

```
NSLog((NSString *)&__NSConstantStringImpl__var_folders_gm_0jk35cwn1d3326x0061qym280000gn_T_main_a5cecc_mi_0, NSStringFromClass(((Class (*)(id, SEL))(void *)objc_msgSend)((id)self, sel_registerName("class"))));

   NSLog((NSString *)&__NSConstantStringImpl__var_folders_gm_0jk35cwn1d3326x0061qym280000gn_T_main_a5cecc_mi_1, NSStringFromClass(((Class (*)(__rw_objc_super *, SEL))(void *)objc_msgSendSuper)((__rw_objc_super){ (id)self, (id)class_getSuperclass(objc_getClass("Son")) }, sel_registerName("class"))));
```
从上面的代码中，我们可以发现在调用 [self class] 时，会转化成 objc_msgSend函数。看下函数定义：

```
id objc_msgSend(id self, SEL op, ...)
```
我们把 self 做为第一个参数传递进去。

而在调用 [super class]时，会转化成 objc_msgSendSuper函数。看下函数定义:

```
id objc_msgSendSuper(struct objc_super *super, SEL op, ...)
```
第一个参数是 objc_super 这样一个结构体，其定义如下:

```
struct objc_super {
      __unsafe_unretained id receiver;
      __unsafe_unretained Class super_class;
};
```
结构体有两个成员，第一个成员是 receiver, 类似于上面的 objc_msgSend函数第一个参数self 。第二个成员是记录当前类的父类是什么。

所以，当调用 ［self class] 时，实际先调用的是 objc_msgSend函数，第一个参数是 Son当前的这个实例，然后在 Son 这个类里面去找 - (Class)class这个方法，没有，去父类 Father里找，也没有，最后在 NSObject类中发现这个方法。而 - (Class)class的实现就是返回self的类别，故上述输出结果为 Son。

objc Runtime开源代码对- (Class)class方法的实现:

```
- (Class)class {
   return object_getClass(self);
}
```
而当调用 [super class]时，会转换成objc_msgSendSuper函数。第一步先构造 objc_super 结构体，结构体第一个成员就是 self 。 第二个成员是 (id)class_getSuperclass(objc_getClass(“Son”)) , 实际该函数输出结果为 Father。

第二步是去 Father这个类里去找 - (Class)class，没有，然后去NSObject类去找，找到了。最后内部是使用 objc_msgSend(objc_super->receiver, @selector(class))去调用，

此时已经和[self class]调用相同了，故上述输出结果仍然返回 Son。

参考链接：微博@Chun_iOS的博文[刨根问底Objective－C Runtime（1）－ Self & Super](http://parking.zunmi.cn/?acct=144&site=chun.tips/)


## 23.`_objc_msgForward` 函数是做什么的，直接调用它将会发生什么？



## 24.runtime如何实现weak变量的自动置nil？

- runtime 对注册的类， 会进行布局，对于 weak 对象会放入一个 hash 表中。 用 weak 指向的对象内存地址作为 key，当此对象的引用计数为0的时候会 dealloc，假如 weak 指向的对象内存地址是a，那么就会以a为键， 在这个 weak 表中搜索，找到所有以a为键的 weak 对象，从而设置为 nil。
- __weak引用的解除时间:
    * 对象的内存销毁时间表，分四个步骤：

```
// 对象的内存销毁时间表
// http://weibo.com/luohanchenyilong/ (微博@iOS程序犭袁)
// https://github.com/ChenYilong
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

- RunLoop只能运行在一种mode下，如果要换mode，当前的loop也需要停下重启成新的。利用这个机制，ScrollView滚动过程中NSDefaultRunLoopMode（kCFRunLoopDefaultMode）的mode会切换到UITrackingRunLoopMode来保证ScrollView的流畅滑动：只能在NSDefaultRunLoopMode模式下处理的事件会影响ScrollView的滑动。
- 如果我们把一个NSTimer对象以NSDefaultRunLoopMode（kCFRunLoopDefaultMode）添加到主运行循环中的时候, ScrollView滚动过程中会因为mode的切换，而导致NSTimer将不再被调度。
- 同时因为mode还是可定制的，所以：

Timer计时会被scrollView的滑动影响的问题可以通过将timer添加到NSRunLoopCommonModes（kCFRunLoopCommonModes）来解决。代码如下：

```
// 

//将timer添加到NSDefaultRunLoopMode中
[NSTimer scheduledTimerWithTimeInterval:1.0
     target:self
     selector:@selector(timerTick:)
     userInfo:nil
     repeats:YES];
//然后再添加到NSRunLoopCommonModes里
NSTimer *timer = [NSTimer timerWithTimeInterval:1.0
     target:self
     selector:@selector(timerTick:)
     userInfo:nil
     repeats:YES];
[[NSRunLoop currentRunLoop] addTimer:timer forMode:NSRunLoopCommonModes];
```


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

- ARC相对于MRC，不是在编译时添加retain/release/autorelease这么简单。应该是编译期和运行期两部分共同帮助开发者管理内存。
- 编译期：ARC用的是更底层的C接口实现的retain/release/autorelease，这样做性能更好，也是为什么不能在ARC环境下手动retain/release/autorelease，同时对同一上下文的同一对象的成对retain/release操作进行优化
- 运行期：ARC也包含运行期组件，这个地方做的优化比较复杂，但也不能被忽略。

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

- 用__block声明外部变量，或者static变量，或者全局变量。
- 默认情况下，在block中访问的外部变量是复制过去的，即：写操作不对原变量生效。但是你可以加上 __block 来让其写操作生效，示例代码如下:

```
__block int a = 0;
   void (^foo)(void) = ^{ 
       a = 1; 
   };
   foo(); 
   //这里，a的值被修改为1
```
- 为什么写操作就生效了？”真正的原因是这样的：
    * 我们都知道：Block不允许修改外部变量的值，这里所说的外部变量的值，指的是栈中指针的内存地址。__block 所起到的作用就是只要观察到该变量被 block 所持有，就将“外部变量”在栈中的内存地址放到了堆中。进而在block内部也可以修改外部变量的值。
- Block不允许修改外部变量的值。Apple这样设计，应该是考虑到了block的特殊性，block也属于“函数”的范畴，变量进入block，实际就是已经改变了作用域。在几个作用域之间进行切换时，如果不加上这样的限制，变量的可维护性将大大降低。又比如我想在block内声明了一个与外部同名的变量，此时是允许呢还是不允许呢？只有加上了这样的限制，这样的情景才能实现。于是栈区变成了红灯区，堆区变成了绿灯区。
- 我们可以打印下内存地址来进行验证：

```
__block int a = 0;
   NSLog(@"定义前：%p", &a);         //栈区
   void (^foo)(void) = ^{
       a = 1;
       NSLog(@"block内部：%p", &a);    //堆区
   };
   NSLog(@"定义后：%p", &a);         //堆区
   foo();
```

```
2016-05-17 02:03:33.559 LeanCloudChatKit-iOS[1505:713679] 定义前：0x16fda86f8
2016-05-17 02:03:33.559 LeanCloudChatKit-iOS[1505:713679] 定义后：0x155b22fc8
2016-05-17 02:03:33.559 LeanCloudChatKit-iOS[1505:713679] block内部： 0x155b22fc8
```
“定义后”和“block内部”两者的内存地址是一样的，我们都知道 block 内部的变量会被 copy 到堆区，“block内部”打印的是堆地址，因而也就可以知道，“定义后”打印的也是堆的地址。
- 那么如何证明“block内部”打印的是堆地址？
    * 把三个16进制的内存地址转成10进制就是：
        * 定义后前：6171559672
        * block内部：5732708296
        * 定义后后：5732708296
    * 中间相差438851376个字节，也就是 418.5M 的空间，因为堆地址要小于栈地址，又因为iOS中一个进程的栈区内存只有1M，Mac也只有8M，显然a已经是在堆区了。这也证实了：a 在定义前是栈区，但只要进入了 block 区域，就变成了堆区。这才是 __block 关键字的真正作用。
- __block 关键字修饰后，int类型也从4字节变成了32字节，这是 Foundation 框架 malloc 出来的。这也同样能证实上面的结论。（PS：居然比 NSObject alloc 出来的 16 字节要多一倍）。
- 理解到这是因为堆栈地址的变更，而非所谓的“写操作生效”，这一点至关重要，要不然你如何解释下面这个现象：
- 以下代码编译可以通过，并且在block中成功将a的从Tom修改为Jerry。

```
NSMutableString *a = [NSMutableString stringWithString:@"Tom"];
   NSLog(@"\n 定以前：------------------------------------\n\
         a指向的堆中地址：%p；a在栈中的指针地址：%p", a, &a);               //a在栈区
   void (^foo)(void) = ^{
       a.string = @"Jerry";
       NSLog(@"\n block内部：------------------------------------\n\
        a指向的堆中地址：%p；a在栈中的指针地址：%p", a, &a);               //a在栈区
       a = [NSMutableString stringWithString:@"William"];
   };
   foo();
   NSLog(@"\n 定以后：------------------------------------\n\
         a指向的堆中地址：%p；a在栈中的指针地址：%p", a, &a);               //a在栈区
```

![image](https://camo.githubusercontent.com/548c6cfd7a1d7084da25be9d4ee76e51a907fd84/687474703a2f2f6936362e74696e797069632e636f6d2f333465756863792e6a7067)

- 这里的a已经由基本数据类型，变成了对象类型。block会对对象类型的指针进行copy，copy到堆中，但并不会改变该指针所指向的堆中的地址，所以在上面的示例代码中，block体内修改的实际是a指向的堆中的内容。
- 但如果我们尝试像上面图片中的65行那样做，结果会编译不通过，那是因为此时你在修改的就不是堆中的内容，而是栈中的内容。
- 上文已经说过：Block不允许修改外部变量的值，这里所说的外部变量的值，指的是栈中指针的内存地址。栈区是红灯区，堆区才是绿灯区。

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
- 先查找_foo, 如果没有再查找foo, 如果都没有则调用 
setValue:forUndefinedKey:
- 具体分析：
    
    当调用 setValue：属性值 forKey：@“key” 的代码时，底层的执行机制如下：
    * 首先搜索set<Key>:方法，如果成员用@property，@synthsize处理，因为@synthsize告诉编译器自动生成set<Key>:格式的setter方法，所以这种情况下会直接搜索到。注意：这里的<Key>是指成员名，而且首字母大写，下同；
    * 上面的setter方法没有找到，如果类方法accessInstanceVariablesDirectly返YES(注：这是NSKeyValueCodingCatogery中实现的类方法，默认实现为返回YES)。那么按_<key>，_is<Key>，<key>，is<key>的顺序搜索成员名。
    * 如果找到设置成员的值，如果没有调用setValue:forUndefinedKey:。
    
    当调用ValueforKey：@”name“的代码时，KVC对key的搜索方式不同于setValue：属性值 forKey：@”name“，其搜索方式如下
    * 首先按get<Key>,<key>,is<Key>的顺序方法查找getter方法，找到的话会直接调用。如果是BOOL或者int等值类型， 会做NSNumber转换
    * 如果上面的getter没有找到，KVC则会查找countOf<Key>,objectIn<Key>AtIndex,<Key>AtIndex格式的方法。如果countOf<Key>和另外两个方法中的要个被找到，那么就会返回一个可以响应NSArray所的方法的代理集合(它是NSKeyValueArray，是NSArray的子类)，调用这个代理集合的方法，或者说给这个代理集合发送NSArray的方法，就会以countOf<Key>,objectIn<Key>AtIndex,<Key>AtIndex这几个方法组合的形式调用。还有一个可选的get<Ket>:range:方法。所以你想重新定义KVC的一些功能，你可以添加这些方法，需要注意的是你的方法名要符合KVC的标准命名方法，包括方法签名。
    * 如果上面的方法没有找到，那么会查找countOf<Key>，enumeratorOf<Key>,memberOf<Key>格式的方法。如果这三个方法都找到，那么就返回一个可以响应NSSet所的方法的代理集合，以送给这个代理集合消息方法，就会以countOf<Key>，enumeratorOf<Key>,memberOf<Key>组合的形式调用。
    * 如果还没有找到，再检查类方法+ (BOOL)accessInstanceVariablesDirectly,如果返回YES(默认行为)，那么和先前的设值一样，会按_<key>,_is<Key>,<key>,is<Key>的顺序搜索成员变量名，这里不推荐这么做，因为这样直接访问实例变量破坏了封装性，使代码更脆弱。如果重写了类方法+ (BOOL)accessInstanceVariablesDirectly返回NO的话，那么会直接调用valueForUndefinedKey。

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

- kvo支持实例变量
- 分析：
    * [手动设定实例变量的KVO实现监听](https://yq.aliyun.com/articles/30483)

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

# 在微博[@iOS程序犭袁](https://weibo.com/luohanchenyilong/)的答案整理中多出来的题整理如下

## 54. runtime如何通过selector找到对应的IMP地址？（分别考虑类方法和实例方法）

- 每一个类对象中都一个方法列表,方法列表中记录着方法的名称,方法实现,以及参数类型,其实selector本质就是方法名称,通过这个方法名称就可以在方法列表中找到对应的方法实现.

## 55. 使用runtime Associate方法关联的对象，需要在主对象dealloc的时候释放么？

- 无论在MRC下还是ARC下均不需要。
- 2011年版本的Apple API 官方文档 - Associative References 一节中有一个MRC环境下的例子：
```
// 在MRC下，使用runtime Associate方法关联的对象，不需要在主对象dealloc的时候释放
// http://weibo.com/luohanchenyilong/ (微博@iOS程序犭袁)
// https://github.com/ChenYilong
// 摘自2011年版本的Apple API 官方文档 - Associative References 

static char overviewKey;
 
NSArray *array =
    [[NSArray alloc] initWithObjects:@"One", @"Two", @"Three", nil];
// For the purposes of illustration, use initWithFormat: to ensure
// the string can be deallocated
NSString *overview =
    [[NSString alloc] initWithFormat:@"%@", @"First three numbers"];
 
objc_setAssociatedObject (
    array,
    &overviewKey,
    overview,
    OBJC_ASSOCIATION_RETAIN
);
 
[overview release];
// (1) overview valid
[array release];
// (2) overview invalid
```
文档指出
> At point 1, the string overview is still valid because the OBJC_ASSOCIATION_RETAIN policy specifies that the array retains the associated object. When the array is deallocated, however (at point 2), overview is released and so in this case also deallocated.

我们可以看到，在[array release];之后，overview就会被release释放掉了。

既然会被销毁，那么具体在什么时间点？
> 根据 WWDC 2011, Session 322 (第36分22秒) 中发布的内存销毁时间表，被关联的对象在生命周期内要比对象本身释放的晚很多。它们会在被 NSObject -dealloc 调用的 object_dispose() 方法中释放。

对象的内存销毁时间表，分四个步骤：

```
// 对象的内存销毁时间表
// http://weibo.com/luohanchenyilong/ (微博@iOS程序犭袁)
// https://github.com/ChenYilong
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

## 56. objc中的类方法和实例方法有什么本质区别和联系？

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
