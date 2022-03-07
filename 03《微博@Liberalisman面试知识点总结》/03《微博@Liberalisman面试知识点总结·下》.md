# iOSInterviewQuestion
## 微博@Liberalisman面试知识点总结（附答案）
- 03《微博@Liberalisman面试知识点总结》，面试题来源是微博[@Liberalisman](https://weibo.com/1743643682/)的面试题知识点总结；
- 如有纰漏，请向微博[@爱吃兔兔的胡萝卜吖](https://weibo.com/6447187962/)反馈。

### 推荐书目
- 1.《Effective Objective-C 2.0》
- 2.《Objective-C 高级编程》
- 3.《程序员的自我修养》
- 4.《图解HTTP》
- 5.《高性能iOS应用开发》
- 6.《算法图解》
- 7.《剑指Offer》）

## 项目架构
### 1.什么是 MVC?
![image](https://upload-images.jianshu.io/upload_images/1653926-9abf7d3219aa5b1c.png?imageMogr2/auto-orient/strip|imageView2/2/w/974)

- 视图（View）：用户界面。
- 控制器（Controller）：业务逻辑
- 模型（Model）：数据保存
- 各部分之间的通信方式如下
    * View 传送指令到 Controller
    * Controller 完成业务逻辑后，要求 Model 改变状态
    * Model 将新的数据发送到 View，用户得到反馈
- MVC的弊端
    * 厚重的View Controller
        * M：模型model的对象通常非常的简单。根据Apple的文档，model应包括数据和操作数据的业务逻辑。而在实践中，model层往往非常薄，不管怎样，model层的业务逻辑不应被拖入到controller。
        * V：视图view通常是UIKit控件（component，这里根据习惯译为控件）或者编码定义的UIKit控件的集合。View的如何构建（PS：IB或者手写界面）何必让Controller知晓，同时View不应该直接引用model（PS：现实中，你懂的！），并且仅仅通过IBAction事件引用controller。业务逻辑很明显不归入view，视图本身没有任何业务。
        * C：控制器controller。Controller是app的“胶水代码”：协调模型和视图之间的所有交互。控制器负责管理他们所拥有的视图的视图层次结构，还要响应视图的loading、appearing、disappearing等等，同时往往也会充满我们不愿暴露的model的模型逻辑以及不愿暴露给视图的业务逻辑。网络数据的请求及后续处理，本地数据库操作，以及一些带有工具性质辅助方法都加大了Massive View Controller的产生。
    * 遗失（无处安放）的网络逻辑
        * 苹果使用的MVC的定义是这么说的：所有的对象都可以被归类为一个model，一个view，或是一个controller。
        * 你可能试着把它放在Model对象里，但是也会很棘手，因为网络调用应该使用异步，这样如果一个网络请求比持有它的model生命周期更长，事情将变的复杂。显然View里面做网络请求那就更格格不入了，因此只剩下Controller了。若这样，这又加剧了Massive View Controller的问题。若不这样，何处才是网络逻辑的家呢？
    * 较差的可测试性
        * 由于View Controller混合了视图处理逻辑和业务逻辑，分离这些成分的单元测试成了一个艰巨的任务。

### 2.什么是 MVVM?
- 一种可以很好地解决Massive View Controller问题的办法就是将 Controller 中的展示逻辑抽取出来，放置到一个专门的地方，而这个地方就是 viewModel 。MVVM衍生于MVC，是对 MVC 的一种演进，它促进了 UI 代码与业务逻辑的分离。它正式规范了视图和控制器紧耦合的性质，并引入新的组件。他们之间的结构关系如下：

![image](https://upload-images.jianshu.io/upload_images/1653926-7ed45d1af126df79.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200)

- MVVM 的基本概念
    * 在MVVM 中，view 和 view controller正式联系在一起，我们把它们视为一个组件
    * view 和 view controller 都不能直接引用model，而是引用视图模型（viewModel）
    * viewModel 是一个放置用户输入验证逻辑，视图显示逻辑，发起网络请求和其他代码的地方
    * 使用MVVM会轻微的增加代码量，但总体上减少了代码的复杂性
- MVVM 的注意事项
    * view 引用viewModel ，但反过来不行（即不要在viewModel中引入#import UIKit.h，任何视图本身的引用都不应该放在viewModel中）
    * viewModel 引用model，但反过来不行
- MVVM 的使用建议
    * MVVM 可以兼容你当下使用的MVC架构。
    * MVVM 增加你的应用的可测试性。
    * MVVM 配合一个绑定机制效果最好
    * viewController 尽量不涉及业务逻辑，让 viewModel 去做这些事情。
    * viewController 只是一个中间人，接收 view 的事件、调用 viewModel 的方法、响应 viewModel 的变化。
    * viewModel 绝对不能包含视图 view（UIKit.h），不然就跟 view 产生了耦合，不方便复用和测试。
    * viewModel之间可以有依赖。
    * viewModel避免过于臃肿，否则重蹈Controller的覆辙，变得难以维护。
- MVVM 的优势
    * 低耦合：View 可以独立于Model变化和修改，一个 viewModel 可以绑定到不同的 View 上
    * 可重用性：可以把一些视图逻辑放在一个 viewModel里面，让很多 view 重用这段视图逻辑
    * 独立开发：开发人员可以专注于业务逻辑和数据的开发 viewModel，设计人员可以专注于页面设计
    * 可测试：通常界面是比较难于测试的，而 MVVM 模式可以针对 viewModel来进行测试
- MVVM 的弊端
    * 数据绑定使得Bug 很难被调试。你看到界面异常了，有可能是你 View 的代码有 Bug，也可能是 Model 的代码有问题。数据绑定使得一个位置的 Bug 被快速传递到别的位置，要定位原始出问题的地方就变得不那么容易了。
    * 对于过大的项目，数据绑定和数据转化需要花费更多的内存（成本）。主要成本在于：
        * 数组内容的转化成本较高：数组里面每项都要转化成Item对象，如果Item对象中还有类似数组，就很头疼。
        * 转化之后的数据在大部分情况是不能直接被展示的，为了能够被展示，还需要第二次转化。
        * 只有在API返回的数据高度标准化时，这些对象原型（Item）的可复用程度才高，否则容易出现类型爆炸，提高维护成本。
    * 调试时通过对象原型查看数据内容不如直接通过NSDictionary/NSArray直观。
    * 同一API的数据被不同View展示时，难以控制数据转化的代码，它们有可能会散落在任何需要的地方。
- MVVM 模式将 Presenter改名为ViewModel，基本上与 MVP 模式完全一致。
- 唯一的区别是，它采用双向绑定（data-binding）：View的变动，自动反映在 ViewModel，反之亦然。
- MVVM的优势就是，任务均摊每部分都承担各自的责任，结构清晰更加符合软件设计原则
- 其次就是可测试性强，我们只需要测试ViewModel就能够轻易的测试UI上的问题

### 3.什么是 MVP?
- MVP 模式将 Controller改名为Presenter，同时改变了通信方向。
- 各部分之间的通信，都是双向的。
- View 与 Model 不发生联系，都通过 Presenter 传递。
- View 非常薄，不部署任何业务逻辑，称为"被动视图"（Passive View），即没有任何主动性，而 Presenter非常厚，所有逻辑都部署在那里。

### 4.什么是 CDD?
### 5.项目的组件化？
#### 1.说一下你了解的项目组件化方案？
#### 2.什么样的团队及项目适合采用组件化的形式进行开发？
#### 3.组件之间的通信方式。
#### 4.各组件之间的解耦。
### 6.还了解哪些项目架构？你之前所在公司的架构师什么样的，简单说一下？
### 7.从宏观上来讲 App 可以分为哪些层？
### 8.多工程连编之静态库


## iOS设计模式
### 1.编程中的六大设计原则？
- 单一职责原则
    * 通俗地讲就是一个类只做一件事
        * CALayer：动画和视图的显示。
        * UIView：只负责事件传递、事件响应。
- 开闭原则
    * 对修改关闭，对扩展开放。
    * 要考虑到后续的扩展性，而不是在原有的基础上来回修改
- 接口隔离原则
    * 使用多个专门的协议、而不是一个庞大臃肿的协议
        * UITableviewDelegate
        * UITableViewDataSource
- 依赖倒置原则
    * 抽象不应该依赖于具体实现、具体实现可以依赖于抽象。
    * 调用接口感觉不到内部是如何操作的
- 里氏替换原则
    * 父类可以被子类无缝替换，且原有的功能不受任何影响，例如 KVO
- 迪米特法则
    * 一个对象应当对其他对象尽可能少的了解，实现高聚合、低耦合

### 2.如何设计一个图片缓存框架？
- 可以模仿 SDWebImage 来实现。
- 构成
    * Manager
    * 内存缓存
    * 磁盘缓存
    * 网络下载
    * Code Manager
        * 图片解码
        * 图片解压缩
        * 图片的存储是以图片的单向 hash 值为 Key
- 内存设计需要考虑的问题
    * 存储的 Size
        * 因为内存的空间有限，我们针对不同尺寸的图片，给出不同的方案
        * 10K 以下的50个
        * 100Kb 以下的20个
        * 100kb 以上的10个
    * 淘汰的策略
        * 内存的淘汰策略采取LRU（最近最少使用算法）
        * 触发淘汰策略的时机有三种
            * 定期检查（不建议，耗性能）
            * 提高检查触发频率（一定要注意开销）
                * 前后台切换的时候
                * 每次读写的时候
- 磁盘设计需要考虑的问题
    * 存储方式
    * 大小限制（有固定的大小）
    * 移除策略（可以设置为7天或者15天）
- 网络设计需要考虑的问题
    * 图片请求的最大并发量
    * 请求超时策略
    * 请求优先级
- 图片解码
    * 应用 策略模式，针对 jpg、png、gif 等不同的图片格式进行解码
    * 图片解码的时机
        * 在 子线程 图片刚下载完时
        * 在 子线程 刚从磁盘读取完时
        * 避免在主线程解压缩、解码，避免卡顿

### 3.如何设计一个时长统计框架？
- 记录器
    * 页面式记录器
    * 流式记录器
    * 自定义式
- 记录管理者
    * 内存记录缓存
    * 磁盘存储
    * 上传器
- 如何降低数据的丢失率？
    * 定期写入磁盘
    * 每当达到某个值的时候，就写入磁盘
- 记录上传的时机
    * 前后台切换的时候可以上传
    * 从无网到有网切换的时候可以上传
- 上传时机的选择
    * 立即上传
    * 定时上传
    * 延时上传

### 4.如何实现 App 换肤（夜间模式）？
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
### 补充：单例弊端？
- 优点：
    * 一个类只被实例化一次，提供了对唯一实例的受控访问。
    * 节省系统资源
    * 允许可变数目的实例。
- 缺点：
    * 一个类只有一个对象，可能造成责任过重，在一定程度上违背了“单一职责原则”。
    * 由于单利模式中没有抽象层，因此单例类的扩展有很大的困难。
    * 滥用单例将带来一些负面问题，如为了节省资源将数据库连接池对象设计为的单例类，可能会导致共享连接池对象的程序过多而出现连接池溢出；如果实例化的对象长时间不被利用，系统会认为是垃圾而被回收，这将导致对象状态的丢失。

### 16.类工厂模式

## 数据存储
### 1.如何判断一个文件在沙盒中是否存在？
- 通常我们在模拟器中运行项目时，如果需要查看沙盒中的文件，只需要按住command+shift+g，然后将文件路径复制进去点击前往，就能查看到沙盒中的文件
- 在真机测试时查看沙盒
    * 点击xcode菜单中的window选项，然后选择Devices and Simulators选项
    * 然后窗口中的TeachersSide就是在真机测试运行的项目。
    * 然后Download文件
    * 然后显示包内容

### 2.数据持久化的几个方案（fmdb用没用过）
- NSUserDefaults
- plist（属性列表）
- NSKeyedArchiver（对象归档）
- iOS的嵌入式关系数据库SQLite3
- 苹果公司提供的持久化工具 Core Data

首先介绍沙盘
- 沙盒目录结构:
    * Documents：保存应用运行时生成的需要持久化的数据，iTunes同步设备时 会 备份该目录。例如，游戏应用可将游戏存档保存在该目录
    * tmp：保存应用运行时所需的临时数据，使用完毕后再将相应的文件从该目录删除。应用没有运行时，系统也可能会清除该目录下的文件。iTunes同步设备时 不会 备份该目录
    * Library/Caches：保存应用运行时生成的需要持久化的数据，iTunes同步设备时 不会 备份该目录。一般存储体积大、不需要备份的非重要数据
    * Library/Preference：保存应用的所有偏好设置，iOS的Settings(设置)应用 会 在该目录中查找应用的设置信息。iTunes同步设备时 会 备份该目录

NSUserDefaults

```
static NSString* const key = @"key";
[[NSUserDefaults standardUserDefaults] setValue:@"YES" forKey:key];
[NSUserDefaults standardUserDefaults] valueForKey:key]
[userDefaults removeObjectForKey:key];
[userDefaults synchronize];
```
上面的示例代码基本就是NSUserDefaults所有用法了，虽然很简单，但还是有几点需要注意：
    * 建议将所有的的key单独存放（好处自己领会）
    * NSUserDefaults可以存储的数据类型包括：NSData、NSString、NSNumber、NSDate、NSArray、NSDictionary。如果要存储其他类型，则需要转换为前面的类型，才能用NSUserDefaults存储。之前碰到个坑就是从服务器拿到数据部分用这种方式存储，服务器返回NSNull,我们这边也没有model层转，就直接存储了，导致app卡掉但并没有闪退之类，就是线程卡死的情况
    * 同步问题，在适当的时候同步。因为synchronize的开销可能会很大，因为要比较内存中和存储中的所有用户偏好默认值，如果有好几百个key value 同步是非常消耗性能的。
    * 偏好设置是专门用来保存应用程序的配置信息的，（ 用过Settings.bundle的应该都很熟悉），所以一般不要在偏好设置中保存其他数据。
    * 偏好设置会将所有数据保存到同一个文件中。即preference目录下的一个以此应用包名来命名的plist文件。

plist
首先需要知道什么是序列化对象（serialized object）：指可以被转换为字节流以便于存储到文件中或通过网络进行传输的对象

```
/**
 *  获取存储路径
 */
- (NSString*)dataFilePath {
    NSArray *paths = NSSearchPathForDirectoriesInDomains(NSDocumentDirectory, NSUserDomainMask, YES);
    NSString *documentDirectory = paths[0];
    return [documentDirectory stringByAppendingPathComponent:@"data.plist"];//nsstring真强大
}
```
我们在app处于非活跃状态时存储一些东东

```
UIApplication* app = [UIApplication sharedApplication];
[[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(appWillResignActive:) name:UIApplicationWillResignActiveNotification object:app];

- (void)appWillResignActive:(NSNotification*)notification {
    NSString* filePath = [self dataFilePath];
    NSArray* arr = @[@1,@2,@3,@4];
    [arr writeToFile:filePath atomically:YES];
}
```
在我们需要这些东东的时候从文件中读取

```
NSString* filePath = [self dataFilePath];
if ([[NSFileManager defaultManager]fileExistsAtPath:filePath]) {
    NSArray* arr = [[NSArray alloc]initWithContentsOfFile:filePath];
}
```

NSKeyedArchiver

在Cocoa中，Archiver是另一种形式的序列化，是任何对象都可实现的更常规的类型

说明：

只有遵守了NSCoding或 NSSecureCoding（更为安全的归档协议）协议,并且实现了协议里归档与解归档的方法的的类创建的对象才能够进行归档
最好也实现以下NSCopying，NSCopying与NSCoding一起实现好处在于允许复制对象，使用数据模型对象时有较大的灵活性


```
#import <Foundation/Foundation.h>
@interface FourLines : NSObject<NSCoding,NSCopying>

@property(copy,nonatomic)NSArray* lines;

@end

#import "FourLines.h"

//编解码的key
static NSString* const klinesKey = @"klinesKey";

@implementation FourLines

#pragma mark -  NSCoding

- (void)encodeWithCoder:(NSCoder *)aCoder {
    [aCoder encodeObject:self.lines forKey:klinesKey];
}

- (nullable instancetype)initWithCoder:(NSCoder *)aDecoder {
    self = [super init];
    if (self) {
        self.lines = [aDecoder decodeObjectForKey:klinesKey];
    }
    return self;
}

#pragma mark -  NSCopying 

- (id)copyWithZone:(nullable NSZone *)zone {
    FourLines* copy = [[[self class]allocWithZone:zone]init];
    NSMutableArray* linesCopy = [NSMutableArray array];
    for (id line in self.lines) {
        [linesCopy addObject:[line copyWithZone:zone]];
    }
    copy.lines = linesCopy;
    return copy;
}

@end
```
写入数据，编码：文件路径还是用上面代码中定义的文件路径

```
- (void)appWillResignActive:(NSNotification*)notification {
    NSString* filePath = [self dataFilePath];
    FourLines* lines = [[FourLines alloc]init];
    lines.lines = @[@"a",@"b",@"c",@"d"];
    NSMutableData* data = [[NSMutableData alloc]init];
    NSKeyedArchiver* archiver = [[NSKeyedArchiver alloc]initForWritingWithMutableData:data];
    [archiver encodeObject:lines forKey:kRootKey];
    [archiver finishEncoding];
    [data writeToFile:filePath atomically:YES];  
}
```
读取数据，解码：

```
NSString* filePath = [self dataFilePath];
 if ([[NSFileManager defaultManager]fileExistsAtPath:filePath]) {
        NSData* data = [[NSMutableData alloc]initWithContentsOfFile:filePath];
        NSKeyedUnarchiver* unarchiver = [[NSKeyedUnarchiver alloc]initForReadingWithData:data];
        FourLines* four = [unarchiver decodeObjectForKey:kRootKey];
        [unarchiver finishDecoding];
        for (int i = 0; i < 4; i++) {
            //to do
        }
}

UIApplication* app = [UIApplication sharedApplication];
[[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(appWillResignActive:) name:UIApplicationWillResignActiveNotification object:app];
```
fmdb（iOS平台的SQLite数据库框架）

建表以及关闭表

使用数据库的第一件事，就是建立一个数据库。要注意的是，在iOS环境下，只有document directory 是可以进行读写的。在写程序时用的那个Resource资料夹底下的东西都是read-only。因此，建立的资料库要放在document 资料夹下。方法如下：


```
//建表
    NSString *doc = [NSSearchPathForDirectoriesInDomains(NSDocumentDirectory, NSUserDomainMask, YES) lastObject];
    NSLog(@"doc = %@", doc);
    NSString *fileName = [doc stringByAppendingPathComponent:@"device.sqlite"];
    FMDatabase *db = [FMDatabase databaseWithPath:fileName];
    if ([db open]) {
        BOOL result = [db executeUpdate:@"CREATE TABLE IF NOT EXISTS Device (deviceID text, deviceName text, deviceType integer, deviceStatus integer);"];
        if (result) {
            NSLog(@"创建表成功");
        } else {
            NSLog(@"建表失败");
        }
    }

```

这样简单的操作就已经完成了数据库的创建，每一行代码都很好理解，先是找到程序在沙盒中的路径，之后填写数据库的名字，完成创建。如果创建数据库成功，那么我们就创建一个名字叫Device的表，这个设备表里有 deviceID, deviceName, deviceType, deviceStatus 四个字段，他们的类型分别是text、text、integer、integer。

### 3.简要介绍沙盘
- 沙盒目录结构:
    * Documents：保存应用运行时生成的需要持久化的数据，iTunes同步设备时 会 备份该目录。例如，游戏应用可将游戏存档保存在该目录
    * tmp：保存应用运行时所需的临时数据，使用完毕后再将相应的文件从该目录删除。应用没有运行时，系统也可能会清除该目录下的文件。iTunes同步设备时 不会 备份该目录
    * Library/Caches：保存应用运行时生成的需要持久化的数据，iTunes同步设备时 不会 备份该目录。一般存储体积大、不需要备份的非重要数据
    * Library/Preference：保存应用的所有偏好设置，iOS的Settings(设置)应用 会 在该目录中查找应用的设置信息。iTunes同步设备时 会 备份该目录

### 4.Sqlite3
#### 1.简单说一下 Sqlite3
#### 2.Sqlite3 常用的执行语句
### 3.Sqlite3在不同版本的APP，数据库结构变化了，如何处理?
### 5.FMDB (Sqlite3 的封装)
### 6.Realm
### 7.NSKeyArchieve
### 8.Preperfence
### 9.Plist
### 10.CoreDate
### 11.Keychain
### 12.UIPasteBoard
### 13.FoundationDB
### 14.LRU(最少最近使用)缓存


## WebView
### 1.说一下 JS 和 OC 互相调用的几种方式？
#### UIWebView 拦截 URL
##### JS 调用原生 OC
- 我们可以利用 JS 发起一个假的 URL 请求，然后利用UIWebView的代理方法拦截这次请求，然后再做相应的处理。

```
- (BOOL)webView:(UIWebView *)webView shouldStartLoadWithRequest:(NSURLRequest *)request navigationType:(UIWebViewNavigationType)navigationType {
    NSURL * url = [request URL];
    if ([[url scheme] isEqualToString:@"firstclick"]) {  // firstClick://shareClick?title=分享的标题&content=分享的内容&url=链接地址&imagePath=图片地址
        NSArray *params = [url.query componentsSeparatedByString:@"&"];
        
        NSMutableDictionary *tempDict = [NSMutableDictionary dictionary];
        NSMutableString *strM = [NSMutableString string];
        for (NSString *paramStr in params) {
            NSArray *dictArray = [paramStr componentsSeparatedByString:@"="];
            if (dictArray.count > 1) {
                NSString *decodeValue = [dictArray[1] stringByReplacingPercentEscapesUsingEncoding:NSUTF8StringEncoding];
                decodeValue = [decodeValue stringByRemovingPercentEncoding];
                [tempDict setObject:decodeValue forKey:dictArray[0]];
                [strM appendString:decodeValue];
            }
        }
        UIAlertView *alertView = [[UIAlertView alloc] initWithTitle:@"这是OC原生的弹出窗" message:strM delegate:self cancelButtonTitle:@"收到" otherButtonTitles:nil];
        [alertView show];
        NSLog(@"tempDic:%@",tempDict);
        return NO;
    }
    return YES;
}
```
- 相关问题：
    * 为什么定义一个loadURL方法，不直接使用window.location.href?
        * 因为如果当前网页正在使用window.location.href加载网页的同时，调用window.location.href去调用 OC 原生方法，会导致加载网页的操作被取消掉。同样的，如果连续使用window.location.href执行两次 OC 原生调用，也有可能导致第一次的操作被取消掉。所以我们使用自定义的loadURL，来避免这个问题。
    * 为什么 loadURL 中的链接，使用统一的 scheme？
        * 便于在 OC 中做拦截处理，减少在 JS 中调用一些 OC 没有实现的方法时，webView 做跳转。我再 OC 拦截 URL 时，根据 scheme即(firstclick）来区分是调用原生的方法还是正常的网页跳转。然后根据host（即//后面的部分shareClick）来区分执行什么操作。
    * 为什么自定义一个asyncAlert方法？
        * 因为有的 JS 调用是需要 OC 返回结果到 JS 的。stringByEvaluatingJavaScriptFromString是一个同步方法，会等待js方法执行完成。而弹出的alert也会阻塞界面等待用户响应，所以他们可能会造成死锁。导致 alert 卡死界面。如果回调的JS是一个耗时操作，那么建议将耗时的操作也放入setTimeout的function中。
> 1.JS中的firstClick,在拦截到的url scheme全都被转化为小写。
2.html 中需要设置编码，否则中文参数可能会出现编码问题。
3.JS用打开一个iFrame的方式替代直接用document.location的方式，以避免多次请求，被替换覆盖的问题。

##### OC 调用 JS

```
NSString *jsStr = [NSString stringWithFormat:@"showAlert('%@')",@"这里是JS中alert弹出的message"];
[self.webView stringByEvaluatingJavaScriptFromString:jsStr];
```

- ==注意：该方法会同步返回一个字符串，因此是一个同步方法，可能会阻塞主线程。==
- 在 html 文件中

```
function showAlert(message) {
  alert(message);
}
```

#### WKWebView拦截 URL
##### JS调用 OC
- 使用WKNavigationDelegate中的代理方法，拦截自定义的 URL 来实现 JS 调用 OC 方法。

```
#pragma mark - WKNavigationDelegate

- (void)webView:(WKWebView *)webView decidePolicyForNavigationAction:(WKNavigationAction *)navigationAction decisionHandler:(void (^)(WKNavigationActionPolicy))decisionHandler {
    NSURL *URL = navigationAction.request.URL;
    NSString *scheme = [URL scheme];
    if ([scheme isEqualToString:@"haleyaction"]) {
        [self handleCustomAction:URL];
        decisionHandler(WKNavigationActionPolicyCancel);
        return;
    }
    decisionHandler(WKNavigationActionPolicyAllow);
}
```
- ==注意点：如果实现了这个代理方法，就必须得调用decisionHandler这个 block，否则会导致 app 奔溃。block 参数是一个枚举值，WKNavigationActionPolicyCancel代表取消加载，相当于UIWebView的代理方法return NO的情况；WKNavigationActionPolicyAllow代表允许加载，相当于UIWebView的代理方法中 return YES的情况。==
- 关于如何区分执行不同的OC方法，也与UIWebView的处理方式一样,通过URL的host来区分执行不同的方法：

```
#pragma mark - dealwith custom action

- (void)handleCustomAction:(NSURL *)URL {
    NSString *host = [URL host];
    
    if ([host isEqualToString:@"shareClick"]) {
        [self share:URL];
    } else if ([host isEqualToString:@"getLocation"]) {
        [self getLocation:URL];
    } else if ([host isEqualToString:@"setBGColor"]) {
        [self setBGColor:URL];
    } else if ([host isEqualToString:@"payAction"]) {
        [self payAction:URL];
    } else if ([host isEqualToString:@"shake"]) {
        [self shakeAction];
    } else if ([host isEqualToString:@"back"]) {
        [self goBack];
    }
}
```
##### OC 调用 JS 方法
- JS 调用OC 方法后，有的操作可能需要将结果返回给JS。这时候就是OC 调用JS 方法的场景。
- WKWebView 提供了一个新的方法evaluateJavaScript:completionHandler:，实现OC 调用JS 等场景。

```
- (void)getLocation:(NSURL *)URL {
    // 获取位置信息
    NSLog(@"原生获取位置信息操作");
    
    // 将结果返回给 JS
    NSString *jsStr = [NSString stringWithFormat:@"setLocation('%@')",@"广东省广州市白云区豪泉大厦"];
    [self.webView evaluateJavaScript:jsStr completionHandler:^(id _Nullable result, NSError * _Nullable error) {
        NSLog(@"%@----%@",result, error);
    }];
}
```
- ==注意点：evaluateJavaScript:completionHandler:没有返回值，JS执行成功还是失败会在completionHandler 中返回。所以使用这个API就可以避免执行耗时的JS，或者alert 导致界面卡住的问题。==

#### JavaScriptCore （UIWebView）
##### JS 调用原生 OC
- 在iOS 7之后，apple添加了一个新的库JavaScriptCore，用来做JS交互，因此JS与原生OC交互也变得简单了许多。
- 首先导入JavaScriptCore库,然后在OC中获取JS的上下文。

```
JSContext *context = [self.webView valueForKeyPath:@"documentView.webView.mainFrame.javaScriptContext"];
```
- 再然后定义好JS需要调用的方法，例如JS要调用share方法：则可以在UIWebView加载url完成后，在其代理方法中添加要调用的share方法：

```
- (void)setupData {
    JSContext *context = [self.webView valueForKeyPath:@"documentView.webView.mainFrame.javaScriptContext"];
    //定义好JS要调用的方法, share就是调用的share方法名
    context[@"share"] = ^() {
        NSLog(@"+++++++Begin Log+++++++");
        NSArray *args = [JSContext currentArguments];
        NSMutableString *strM = [NSMutableString string];
        for (JSValue *jsVal in args) {
            NSLog(@"%@", jsVal.toString);
            [strM appendString:jsVal.toString];
        }
        
        dispatch_async(dispatch_get_main_queue(), ^{
            UIAlertView *alertView = [[UIAlertView alloc] initWithTitle:@"这是OC原生的弹出窗" message:strM delegate:self cancelButtonTitle:@"收到" otherButtonTitles:nil];
            [alertView show];
        });
        
        
        NSLog(@"-------End Log-------");
    };
}
```
##### OC 调用 JS
- OC 调用 JS 方法有多种，首先介绍使用JavaScriptCore框架的方式。
- 方式一：使用JSContext 的方法-evaluateScript，可以实现 OC 调用 JS 方法

```
// 法一
- (void)transferJS {
    JSContext *context = [self.webView valueForKeyPath:@"documentView.webView.mainFrame.javaScriptContext"];
    NSString *textJS = @"showAlert('这里是JS中alert弹出的message')";
    [context evaluateScript:textJS];
}

// 法二
- (void)transferJS {
    NSString *textJS = @"showAlert('这里是JS中alert弹出的message')";
    [[JSContext currentContext] evaluateScript:textJS];
}
```
- 方式二：使用 JSValue 的方法-callWithArguments，也可以实现 OC 调用 JS 方法

```
JSContext *context = [self.webView valueForKeyPath:@"documentView.webView.mainFrame.javaScriptContext"];
[context[@"showAlert"] callWithArguments:@[@"这里是JS中alert弹出的message"]];
```

#### MessageHandler(WKWebView)
- 使用WKWebView的时候，如果想要实现JS调用OC方法，除了拦截URL之外，还有一种简单的方式。那就是利用WKWebView的新特性MessageHandler来实现JS调用原生方法。
##### 怎么使用MessageHandler？
- 创建WKWebViewConfiguration对象，配置各个API对应的MessageHandler。
- WKUserContentController对象可以添加多个scriptMessageHandler。
- 然后在界面即将显示的时候添加MessageHandler

```
- (void)viewWillAppear:(BOOL)animated {
    [super viewWillAppear:animated];
    
    // addScriptMessageHandler 很容易导致循环引用
    // 控制器 强引用了WKWebView,WKWebView copy(强引用了）configuration， configuration copy （强引用了）userContentController
    // userContentController 强引用了 self （控制器）
    [self.webView.configuration.userContentController addScriptMessageHandler:self name:@"ScanAction"];
    [self.webView.configuration.userContentController addScriptMessageHandler:self name:@"Location"];
    [self.webView.configuration.userContentController addScriptMessageHandler:self name:@"Share"];
}
```
- 需要注意的是addScriptMessageHandler很容易引起循环引用，导致控制器无法被释放，所以需要移除MessageHandler

```
- (void)viewWillDisappear:(BOOL)animated {
    [super viewWillDisappear:animated];
    
    // 因此这里要记得移除handlers
    [self.webView.configuration.userContentController removeScriptMessageHandlerForName:@"ScanAction"];
    [self.webView.configuration.userContentController removeScriptMessageHandlerForName:@"Location"];
    [self.webView.configuration.userContentController removeScriptMessageHandlerForName:@"Share"];
}
```
##### 实现协议方法 - JS调用 OC
- 这里实现了两个协议<WKUIDelegate,WKScriptMessageHandler>，WKUIDelegate是因为我在JS中弹出了alert 。WKScriptMessageHandler是因为我们要处理JS调用OC方法的请求。

```
#pragma mark - WKScriptMessageHandler

- (void)userContentController:(WKUserContentController *)userContentController didReceiveScriptMessage:(WKScriptMessage *)message {
    // message.body  --  Allowed types are NSNumber, NSString, NSDate, NSArray,NSDictionary, and NSNull.
    if ([message.name isEqualToString:@"ScanAction"]) {
        [self scanAction];
    } else if ([message.name isEqualToString:@"Location"]) {
        [self getLocation];
    } else if ([message.name isEqualToString:@"Share"]) {
        [self shareWithParams:message.body];
    }
}
```
- WKScriptMessage有两个关键属性name 和 body。
- 因为我们给每一个OC方法取了一个name，那么我们就可以根据name 来区分执行不同的方法。body 中存着JS 要给OC 传的参数。
- 关于参数body的解析，我就举一个body中放字典的例子，其他的稍后可以看demo。
解析JS 调用OC 实现分享的参数：

```
- (void)shareWithParams:(NSDictionary *)params {
    if (![params isKindOfClass:[NSDictionary class]]) {
        return;
    }
    NSString *title = [params objectForKey:@"title"];
    NSString *content = [params objectForKey:@"content"];
    NSString *url = [params objectForKey:@"url"];
    
    // 在这里执行分享的操作
    NSLog(@"在这里执行分享的操作");
    
    // 将分享结果返回给js
    NSString *jsStr = [NSString stringWithFormat:@"shareResult('%@','%@','%@')",title,content,url];
    [self.webView evaluateJavaScript:jsStr completionHandler:^(id result, NSError *error) {
        NSLog(@"%@----%@",result, error);
    }];
}
```
- message.boby就是JS里传过来的参数。我们不同的方法先做一下容错性判断。然后正常取值就可以了。

##### 处理HTML中JS调用

```
// 传字典              
function shareClick(){
  window.webkit.messageHandlers.Share.postMessage({title:'测试分享的标题',content:'测试分享的内容',url:'http://www.baidu.com'});
}

function shareResult(channel_id,share_channel,share_url) {
    var content = channel_id+","+share_channel+","+share_url;
    asyncAlert(content);
    document.getElementById("returnValue").value = content;
}
            
function asyncAlert(content) {
    setTimeout(function(){
        alert(content);
    },1);
}
```
##### OC调用JS
- 这里使用WKWebView实现OC调用JS方法与之前说的文章一样，通过- evaluateJavaScript:completionHandler:

```
// 将分享结果返回给js
NSString *jsStr = [NSString stringWithFormat:@"shareResult('%@','%@','%@')",title,content,url];
[self.webView evaluateJavaScript:jsStr completionHandler:^(id _Nullable result, NSError * _Nullable error) {
    NSLog(@"%@----%@",result, error);
}];
```
##### 使用MessageHandler的好处
- 1.在JS中写起来简单，不用再用创建URL的方式那么麻烦了。
- 2.JS传递参数更方便。使用拦截URL的方式传递参数，只能把参数拼接在后面，如果遇到要传递的参数中有特殊字符，如&、=、？等，必须得转换，否则参数解析肯定会出错。

#### WebViewJavascriptBridge(UIWebView)
##### 第一步，使用Pods 将WebViewJavascriptBridge库添加到工程中。
##### 第二步，创建UIWebView和WebViewJavascriptBridge示例

```
#import <WebViewJavascriptBridge.h>

@interface WebBridgeViewController ()
/** webView */
@property(nonatomic, strong)UIWebView *webView;
/** bridge */
@property(nonatomic, strong)WebViewJavascriptBridge *webViewBridge;

@end
```
- 创建UIWebVIew

```
- (void)drawUI {
    self.webView = [[UIWebView alloc] initWithFrame:self.view.bounds];
    [self.view addSubview:self.webView];
    
    NSURL *htmlURL = [[NSBundle mainBundle] URLForResource:@"index.html" withExtension:nil];
    NSURLRequest *request = [NSURLRequest requestWithURL:htmlURL];
    
    // UIWebView 滚动的比较慢，这里设置为正常速度
    self.webView.scrollView.decelerationRate = UIScrollViewDecelerationRateNormal;
    [self.webView loadRequest:request];
}
```
> 这里不需要为UIWebViews设置代理，因为在创建WebViewJavascriptBridge的时候，UIWebView的代理已经被赋值给了WebViewJavascriptBridge。

- 创建WebViewJavascriptBridge
    * 因为WebViewJavascriptBridge实例，在控制器中多个地方用到，因此最好定义一个property或者实例变量存起来。

```
// WebViewJavascriptBridge
self.webViewBridge = [WebViewJavascriptBridge bridgeForWebView:self.webView];
[self.webViewBridge setWebViewDelegate:self];
```
- 然后看看bridgeForWebView:方法是如何实现的

```
+ (instancetype)bridgeForWebView:(id)webView {
    return [self bridge:webView];
}
+ (instancetype)bridge:(id)webView {
#if defined supportsWKWebView
    if ([webView isKindOfClass:[WKWebView class]]) {
        return (WebViewJavascriptBridge*) [WKWebViewJavascriptBridge bridgeForWebView:webView];
    }
#endif
    if ([webView isKindOfClass:[WVJB_WEBVIEW_TYPE class]]) {
        WebViewJavascriptBridge* bridge = [[self alloc] init];
        [bridge _platformSpecificSetup:webView];
        return bridge;
    }
    [NSException raise:@"BadWebViewType" format:@"Unknown web view type."];
    return nil;
}
```
- 其实{-bridgeForWebView }内部先去判断当前使用的是 WKWebView 还是 UIWebView，然后再分别初始化了一个WebViewJavascriptBridge对象，并为其实例变量_webView 和 _base赋值。

##### 第三步，注册js 要调用的Native 功能。

```
- (void)registerNativeFunctions {
    [self registShareFunction];
    
    [self registLocationFunction];
    
    [self registPayFunction];
}

- (void)registShareFunction {
    [self.webViewBridge registerHandler:@"shareClick" handler:^(id data, WVJBResponseCallback responseCallback) {
        // data 的类型与 JS中传的参数有关
        NSDictionary *tempDic = data;
        // 在这里执行分享的操作
        NSString *title = [tempDic objectForKey:@"title"];
        NSString *content = [tempDic objectForKey:@"content"];
        NSString *url = [tempDic objectForKey:@"url"];
        NSLog(@"JS 传递给 OC 的参数:%@",[NSString stringWithFormat:@"分享成功:%@,%@,%@",title,content,url]);
        
        // 将分享的结果返回到JS中
        NSString *result = [NSString stringWithFormat:@"分享成功:%@,%@,%@",title,content,url];
        responseCallback(result);
    }];
}
```
- - (void)registerHandler:(NSString *)handlerName handler:(WVJBHandler)handler 该方法由两个参数：第一个参数handlerName，是对这个功能起的一个别名。第二个参数handler，是一个block，也就是 Native 实现的功能。JS 要调用的 Native 实现其实就是 block 内{}内的代码功能。
- 为了便于维护，我们可以将JS要调用的Native方法都集中到一起，然后单个功能再封装一个方法。

##### 第四步，完成 HTML 必要的 JS 代码
- HTML 中有一个必须要添加的JS方法，然后需要自动调用一次该方法。该方法是：

```
function setupWebViewJavascriptBridge(callback) {
    if (window.WebViewJavascriptBridge) { return callback(WebViewJavascriptBridge); }
    if (window.WVJBCallbacks) { return window.WVJBCallbacks.push(callback); }
    window.WVJBCallbacks = [callback];
    var WVJBIframe = document.createElement('iframe');
    WVJBIframe.style.display = 'none';
    WVJBIframe.src = 'wvjbscheme://__BRIDGE_LOADED__';
    document.documentElement.appendChild(WVJBIframe);
    setTimeout(function() { document.documentElement.removeChild(WVJBIframe) }, 0)
}
```
- 上面这个方法的参数是一个function，这个方法的作用主要是在第一次加载HTML的时候起作用，目的是加载一次wvjbscheme://__BRIDGE_LOADED__，来触发往HTML中注入一些已经写好的JS方法。
- 看看上面的方法与下面这个是不是很相似：

```
function loadURL(url) {
    var iFrame;
    iFrame = document.createElement("iframe");
    iFrame.setAttribute("src", url);
    iFrame.setAttribute("style", "display:none;");
    iFrame.setAttribute("height", "0px");
    iFrame.setAttribute("width", "0px");
    iFrame.setAttribute("frameborder", "0");
    document.body.appendChild(iFrame);
    // 发起请求后这个iFrame就没用了，所以把它从dom上移除掉
    iFrame.parentNode.removeChild(iFrame);
    iFrame = null;
}
```
- 添加完setupWebViewJavascriptBridge方法，需要在JS中主动调用一次该方法：

```
setupWebViewJavascriptBridge(function(bridge) {
     bridge.registerHandler('testJavascriptHandler', function(data, responseCallback) {
        alert('JS方法被调用:'+data);
        responseCallback('js执行过了');
     })
})
```
- Native 需要调用的 JS 功能，也是需要先注册，然后再执行的。如果Native 需要调用的JS 功能有多个，那么这些功能都要在这里先注册，注册之后才能够被Native 调用。
接下来需要好好分析一下JS 中这个方法的作用了。
- 以下是分析的重点
    * 首先调用setupWebViewJavascriptBridge，第一次执行的时候，由于window.WebViewJavascriptBridge和window.WVJBCallbacks都不存在，所以会继续往下执行，将参数callback（它是一个function）装进数组赋值给window.WVJBCallbacks。
    * js 支持动态添加属性并赋值，这里window.WVJBCallbacks=[callback];就是动态添加属性，并赋值。 另外js中的全局变量都可以使用window.xxxx来调用;动态添加的属性也可以不加window.，直接使用
    * WebViewJavascriptBridge 帮助JS调用Native的url 有两种，一种是wvjbscheme://__BRIDGE_LOADED__；而另一种是wvjbscheme://__WVJB_QUEUE_MESSAGE__。前者只有在调用setupWebViewJavascriptBridge的时候执行一次，一般来说这个url 如果没有页面应该只会执行一次。第二种url所有js调用Native 功能时，都会使用到。
    * 在拦截到自定义的url 时，WebViewJavascriptBridge分了三种情况。
3.1 如果是wvjbscheme://__BRIDGE_LOADED__,就往HMTL 中注入已经写好的js，这个js 在WebViewJavascriptBridge_JS中；
3.2 如果是wvjbscheme://__WVJB_QUEUE_MESSAGE__,那就利用stringByEvaluatingJavaScriptFromString，取回调用js中callHandler传进去的参数。
然后再从WebViewJavascriptBridge之前保存的Native 方法对应的block，调用对应的block。

##### 第五步，调用 Native 功能
- 利用之前注入的JS方法callHandler就可以调用Native 功能了。
- 示例代码如下：

```
function shareClick() {
    var params = {'title':'测试分享的标题','content':'测试分享的内容','url':'http://www.baidu.com'};
    WebViewJavascriptBridge.callHandler('shareClick',params,function(response) {
         alert(response);
        document.getElementById("returnValue").value = response;
     });
}
```
- 这里callHandler前的WebViewJavascriptBridge,其实就是上一步注入到JS中的代码中，动态创建属性，动态赋值的属性。如下代码片段可以在WebViewJavascriptBridge_JS中找到。

```
window.WebViewJavascriptBridge = {
  registerHandler: registerHandler,
  callHandler: callHandler,
  disableJavscriptAlertBoxSafetyTimeout: disableJavscriptAlertBoxSafetyTimeout,
  _fetchQueue: _fetchQueue,
  _handleMessageFromObjC: _handleMessageFromObjC
 };
```
- 而callHandler 内部调用了另一个js function _doSend,而_doSend内部其实，就是把handlerName和 参数data，再加上callbackId 装成键值对，然后保存到数组sendMessageQueue，同时加载一次wvjbscheme://__WVJB_QUEUE_MESSAGE__。
到此 利用WebViewJavascriptBridge实现JS 调用iOS Native 就完成了。

##### 第六步，Native 调用 JS 功能
- Native 调用js 的功能，也需要先在js 中为要调用的功能注册一个别名。
- js 注册Native 要调用的功能

```
setupWebViewJavascriptBridge(function(bridge) {
     bridge.registerHandler('testJSFunction', function(data, responseCallback) {
        alert('JS方法被调用:'+data);
        responseCallback('js执行过了');
     })
    // 注册其他的功能
    //bridge.regsiterHandler.....
})
```
- Native 调用功能的别名handlerName

```
//    // 如果不需要参数，不需要回调，使用这个
//    [_webViewBridge callHandler:@"testJSFunction"];
//    // 如果需要参数，不需要回调，使用这个
//    [_webViewBridge callHandler:@"testJSFunction" data:@"一个字符串"];
    // 如果既需要参数，又需要回调，使用这个
    [_webViewBridge callHandler:@"testJSFunction" data:@"一个字符串" responseCallback:^(id responseData) {
        NSLog(@"调用完JS后的回调：%@",responseData);
    }];
```
- 而callHandler 方法又是如何实现调用js 方法的呢？
callHandler 内部是将传递给js 的参数、handlerName、callbackId组合成字典，然后把字典转换成字符串，将转换后的字符串以参数的形式，通过stringByEvaluatingJavaScriptFromString传递给js ，js 中将传递过来的字符串转成json ，然后通过handlerName 获取对应的function执行。
- 关键的几个代码段：

```
// 这里是Native 调用js ，把参数转换为字符串，执行js 中的_handleMessageFromObjC方法。
- (void)_dispatchMessage:(WVJBMessage*)message {
    NSString *messageJSON = [self _serializeMessage:message pretty:NO];
    [self _log:@"SEND" json:messageJSON];
    messageJSON = [messageJSON stringByReplacingOccurrencesOfString:@"\\" withString:@"\\\\"];
    messageJSON = [messageJSON stringByReplacingOccurrencesOfString:@"\"" withString:@"\\\""];
    messageJSON = [messageJSON stringByReplacingOccurrencesOfString:@"\'" withString:@"\\\'"];
    messageJSON = [messageJSON stringByReplacingOccurrencesOfString:@"\n" withString:@"\\n"];
    messageJSON = [messageJSON stringByReplacingOccurrencesOfString:@"\r" withString:@"\\r"];
    messageJSON = [messageJSON stringByReplacingOccurrencesOfString:@"\f" withString:@"\\f"];
    messageJSON = [messageJSON stringByReplacingOccurrencesOfString:@"\u2028" withString:@"\\u2028"];
    messageJSON = [messageJSON stringByReplacingOccurrencesOfString:@"\u2029" withString:@"\\u2029"];
    
    NSString* javascriptCommand = [NSString stringWithFormat:@"WebViewJavascriptBridge._handleMessageFromObjC('%@');", messageJSON];
    if ([[NSThread currentThread] isMainThread]) {
        [self _evaluateJavascript:javascriptCommand];

    } else {
        dispatch_sync(dispatch_get_main_queue(), ^{
            [self _evaluateJavascript:javascriptCommand];
        });
    }
}
```
- 下面这里是找到handlerName对应的function，并执行function。

```
var handler = messageHandlers[message.handlerName];
    if (!handler) {
     console.log("WebViewJavascriptBridge: WARNING: no handler for message from ObjC:", message);
    } else {
     handler(message.data, responseCallback);
    }
}
```
- 到这里 利用WebViewJavascriptBridge 实现Native 调用js 的功能就完成了。
> 注意：JS 有动态参数的特性，调用js 的方法，可以传0个参数，1个参数，N个参数都可以。
例如，我们在js中定义一个test()方法，我们可以调用test()，来执行这个方法；如果有参数要传进来，也可以调用test(xxx)；如果有多个参数，那么就用test(xxx,xxx)。当然如果我们定义的参数是test(a,b,c)，也可以少传参数，或者不传参数调用test()。

##### 总结
- 利用WebViewJavascriptBridge来实现JS与OC的交互的优点：
    * 获取参数时，更方便一些，如果参数中有一些特殊符号或者url带参数，能够很好的解析。
- 一些缺点：
    * 做一次交互，需要执行的js与原生的交互步骤较多，至少有两次。
    * 需要花较多的时间，理解WebViewJavascriptBridge的原理和使用步骤。

#### WebViewJavascriptBridge(WKWebView)

### 2.在使用 WKWedView 时遇到过哪些问题？
#### WKWebView 白屏问题
- 在 UIWebView 上当内存占用太大的时候，App Process 会 crash；而在 WKWebView 上当总体的内存占用比较大的时候，WebContent Process 会 crash，从而出现白屏现象。
- 这个时候 WKWebView.URL 会变为 nil, 简单的 reload 刷新操作已经失效，对于一些长驻的H5页面影响比较大。
- 解决方案：
    * 借助 WKNavigtionDelegate
        * iOS 9以后 WKNavigtionDelegate 新增了一个回调函数：- (void)webViewWebContentProcessDidTerminate:(WKWebView *)webView API_AVAILABLE(macosx(10.11), ios(9.0));当 WKWebView 总体内存占用过大，页面即将白屏的时候，系统会调用上面的回调函数，我们在该函数里执行[webView reload](这个时候 webView.URL 取值尚不为 nil）解决白屏问题。在一些高内存消耗的页面可能会频繁刷新当前页面，H5侧也要做相应的适配操作。
    * 检测 webView.title 是否为空
        * 可以在 viewWillAppear 的时候检测 webView.title 是否为空来 reload 页面。

#### WKWebView Cookie 问题
- WKWebView Cookie 问题在于 WKWebView 发起的请求不会自动带上存储于 NSHTTPCookieStorage 容器中的 Cookie。
- 目前的主要解决方案是：
    * WKWebView loadRequest 前，在 request header 中设置 Cookie, 解决首个请求 Cookie 带不上的问题；
    * 通过 document.cookie 设置 Cookie 解决后续页面(同域)Ajax、iframe 请求的 Cookie 问题；但无法解决302请求的 Cookie 问题

#### WKWebView NSURLProtocol问题
- WKWebView 在独立于 app 进程之外的进程中执行网络请求，请求数据不经过主进程，因此，在 WKWebView 上直接使用 NSURLProtocol 无法拦截请求。

#### WKWebView loadRequest 问题
- 在 WKWebView 上通过 loadRequest 发起的 post 请求 body 数据会丢失：

#### WKWebView 页面样式问题
- 在 WKWebView 适配过程中，我们发现部分H5页面元素位置向下偏移或被拉伸变形，追踪后发现主要是H5页面高度值异常导致：
- 

#### WKWebView 截屏问题
- WKWebView 下通过 -[CALayer renderInContext:]实现截屏的方式失效，需要通过以下方式实现截屏功能：

```
@implementation UIView (ImageSnapshot) 
- (UIImage*)imageSnapshot { 
    UIGraphicsBeginImageContextWithOptions(self.bounds.size,YES,self.contentScaleFactor); 
    [self drawViewHierarchyInRect:self.bounds afterScreenUpdates:YES]; 
    UIImage* newImage = UIGraphicsGetImageFromCurrentImageContext(); 
    UIGraphicsEndImageContext(); 
    return newImage; 
} 
@end
```
- 然而这种方式依然解决不了 webGL 页面的截屏问题，对webGL 页面的截屏结果不是空白就是纯黑图片。无奈之下，我们只能约定一个JS接口，让游戏开发商实现该接口，具体是通过 canvas getImageData()方法取得图片数据后返回 base64 格式的数据，客户端在需要截图的时候，调用这个JS接口获取 base64 String 并转换成 UIImage。

#### WKWebView crash问题
- 暂无

#### 视频自动播放
- WKWebView 需要通过WKWebViewConfiguration.mediaPlaybackRequiresUserAction设置是否允许自动播放，但一定要在 WKWebView 初始化之前设置，在 WKWebView 初始化之后设置无效。
- 
#### goBack API问题
- WKWebView 上调用 -[WKWebView goBack], 回退到上一个页面后不会触发window.onload()函数、不会执行JS。

#### 页面滚动速率
- WKWebView 需要通过scrollView delegate调整滚动速率：

```
- (void)scrollViewWillBeginDragging:(UIScrollView *)scrollView {
     scrollView.decelerationRate = UIScrollViewDecelerationRateNormal;
}
```
参考：[WKWebView 那些坑](https://mp.weixin.qq.com/s/rhYKLIbXOsUJC_n6dt9UfA)

#### WKWebView和UIWebView的区别
- WKWebView 是苹果在 WWDC 2014 上推出的新一代 webView 组件，用以替代 UIKit 中笨重难用、内存泄漏的 UIWebView。WKWebView 拥有60fps滚动刷新率；
- 优点
    * 性能和稳定性的大幅提高
    * 内存占用的减少，大概是UIWebView的1/4 - 1/3
    * 支持更多HTML5、JS特性：允许JavaScript的Nitro的库加载并使用（移动设备的 Safari 使用 Nitro 引擎，但是 UIWebView 不包括 JIT 编译，所以不支持，体验会慢一些）
    * 60fps的刷新率以及内置手势的支持
    * 增加了新的代理方法，可控性更高
    * estimatedProgress属性实现进度条：不需要像UIWebView一样自己做假进度条（通过NJKWebViewProgress和双层代理技术实现），技术复杂度和代码量，根贴近实际加载进度优化好的多。
    * JS交互上更方便
        * 可以和js直接互调函数，不像UIWebView需要第三方库WebViewJavascriptBridge来协助处理和js的交互。
- 缺点
    * 不自带cookie
        * 业界普遍认为 WKWebView 拥有自己的私有存储，不会将 Cookie 存入到标准的 Cookie 容器 NSHTTPCookieStorage 中。会忽略任何的默认网络存储器(NSURLCache, NSHTTPCookieStorage, NSCredentialStorage) 和一些标准的自定义网络请求类(NSURLProtocol,等等.)，导致NSURLCache和NSHTTPCookieStroage无法操作(WKWebView)WebCore进程的缓存和Cookie
        * 实践发现 WKWebView 实例其实也会将 Cookie 存储于 NSHTTPCookieStorage 中，但存储时机有延迟，在iOS 8上，当页面跳转的时候，当前页面的 Cookie 会写入 NSHTTPCookieStorage 中，而在 iOS 10 上，JS 执行 document.cookie 或服务器 set-cookie 注入的 Cookie 会很快同步到 NSHTTPCookieStorage 中，FireFox 工程师曾建议通过 reset WKProcessPool 来触发 Cookie 同步到 NSHTTPCookieStorage 中，实践发现不起作用，并可能会引发当前页面 session cookie 丢失等问题。
    * 不支持自定义NSURLProtocol，否则无法发送POST参数

#### iOS中的WebView如何优化
- WkWebView时间消耗可能的节点
    * 页面中初始化WKWebView时间消耗；
    * WkWebView加载js、css、image等静态资源时间消耗；
    * WKWebView渲染页面时间消耗；
- 对应主要的时间消耗，解决方案如下
    * WKWebView做成单例，常驻内存，避免实例化带来的时间消耗，同时避免大量创建造成的内存消耗；
    * js、css、image等进行离线缓存或提前预加载，避免展示等时候才加载，减少加载静态资源的时间消耗；
    * image可以考虑使用native预加载，WKWebView中的图片由native加载好的进行替换；
    * 关于页面渲染时间消耗，只能将页面尽可能做的简单清晰，在代码优化上多做功夫。重度交互放在native上，WKWebView只做丰富内容的展示；
- 主要设计思想
    * 服务端返回一个头部包含js、css内容的、可以作为所有页面壳资源的壳文件（shell.html），native使用shell以单例的方式实例化一个WKWebView；
    * 当用户在浏览列表页时，接口返回每个页面所包含的image集合、页面body内容（数据接口在稍后给出），App可以选择是否对图片进行预加载以提高WKWebView的响应速度（例如wifi情况下）；
    * 进入包含WkWebView的页面以后，使用列表页中取得的图片和body内容对shell.html中的body内容进行替换，刷新WkWebView内容。也可以根据ID读取本地缓存文件实现内容替换，可操作性较强。
- 核心模块及所需方法
    * 资源管理模块
        * 能够根据接口返回的信息有条件地下载js、css、shell.html等静态资源，存储到指定的位置。
        * 能够对静态资源文件进行管理，包括：删除缓存，更新资源等操作。
        * 能够对已经浏览过的页面数据及相关字段信息进行缓存，能够对这部分资源进行管理，包括：清除老旧信息、对应ID查找指定的页面信息、更新其中的字段信息等。
    * WKWebView单例类
        * 以单例模式生成shell.html文件页面；
        * 能够根据model刷新页面信息；
        * 支持常用的与js的交互能力；
        * 代理方法能够支持获取必要的页面信息；

### 3.是否了解 UIWebView 的插件化？
### 4.是否了解 SFSafariViewController ？


## 音频处理

## 视频处理
### 补充：AVFoundation原理
- AFNetworking 底层原理分析
- AFNetworking是封装的NSURLSession的网络请求，由五个模块组成：分别由NSURLSession,Security,Reachability,Serialization,UIKit五部分组成
- NSURLSession：网络通信模块（核心模块） 对应 AFNetworking中的 AFURLSessionManager和对HTTP协议进行特化处理的AFHTTPSessionManager,AFHTTPSessionManager是继承于AFURLSessionmanager的
- Security：网络通讯安全策略模块 对应 AFSecurityPolicy
- Reachability：网络状态监听模块 对应AFNetworkReachabilityManager
- Seriaalization：网络通信信息序列化、反序列化模块 对应 AFURLResponseSerialization
- UIKit：对于iOS UIKit的扩展库

### AFN3.0与2.0区别，AFN4.0
#### 发展历程
- AFNetworking 1.0建立在NSURLConnection的基础API之上
- AFNetworking 2.0开始使用NSURLConnection的基础API ，以及较新基于NSURLSession的API的选项。
- AFNetworking 3.0现已完全基于NSURLSession的API，这降低了维护的负担，同时支持苹果增强关于NSURLSession提供的任何额外功能。
- AFNetworking 2.X将继续获得关键的隐患和安全补丁，但没有新的功能将被添加。Alamofire(Swift下的网络请求)软件基金会建议，所有的项目迁移到基于NSURLSession的API。

#### 废弃与新增
- 下面的类已从AFNetworking 3.0中废弃：
    * AFURLConnectionOperation
    * AFHTTPRequestOperation
    * AFHTTPRequestOperationManager
- 依次被下面三个类代替了，同时请求方法也跟着改变了
    * AFURLSessionManager
    * AFHTTPSessionManager
    * AFNetworkReachabilityManager
- 下面的类包含基于NSURLConnection的API的内部实现。他们已经被NSURLSession重构:
    * UIImageView+AFNetworking
    * UIWebView+AFNetworking
    * UIButton+AFNetworking

#### 迁移
- AFHTTPRequestOperationManager与AFHTTPSessionManager
    * 如果你以前使用 AFHTTPRequestOperationManager ， 你将需要迁移去使用 AFHTTPSessionManager。 以下的类在两者过渡间并没有变化：
        * securityPolicy
        * requestSerializer
        * responseSerializer
    * 接下来举一个关于AFHTTPSessionManager的简单例子。注意HTTP网络请求返回的不再是AFHTTPRequestOperation, 修改成为了NSURLSessionTask，并且成功和失败的Block块中的参数也变更为了NSURLSessionTask，而不再是AFHTTPRequestOperation。
    * 

### 一个完整直播app功能

![image](https://upload-images.jianshu.io/upload_images/8957764-fc94afcbe56ece0b.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200)

#### 基本概念
- 一个完整直播app原理
    * 直播原理：把主播录制的视频，推送到服务器，在由服务器分发给观众观看。
    * 直播环节：推流端（采集、美颜处理、编码、推流）、服务端处理（转码、录制、截图、鉴黄）、播放器（拉流、解码、渲染）、互动系统（聊天室、礼物系统、赞）
- 一个完整直播app实现流程
    * 1.采集、2.滤镜处理、3.编码、4.推流、5.CDN分发、6.拉流、7.解码、8.播放、9.聊天互动
- 一个完整直播app架构

![image](https://upload-images.jianshu.io/upload_images/304825-54974199408c0cc1.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200)

#### 一个完整直播app技术点

![image](https://upload-images.jianshu.io/upload_images/304825-9b64e9596f3ccdce.jpeg?imageMogr2/auto-orient/strip|imageView2/2/w/1200)

#### 了解流媒体（直播需要用到流媒体）
- 流媒体开发:网络层(socket或st)负责传输，协议层(rtmp或hls)负责网络打包，封装层(flv、ts)负责编解码数据的封装，编码层(h.264和aac)负责图像，音频压缩。
- 帧:每帧代表一幅静止的图像
- GOP:（Group of Pictures）画面组，一个GOP就是一组连续的画面，每个画面都是一帧，一个GOP就是很多帧的集合
    * 直播的数据，其实是一组图片，包括I帧、P帧、B帧，当用户第一次观看的时候，会寻找I帧，而播放器会到服务器寻找到最近的I帧反馈给用户。因此，GOP Cache增加了端到端延迟，因为它必须要拿到最近的I帧
    * GOP Cache的长度越长，画面质量越好
- 码率：图片进行压缩后每秒显示的数据量。
- 帧率：每秒显示的图片数。影响画面流畅度，与画面流畅度成正比：帧率越大，画面越流畅；帧率越小，画面越有跳动感。
    * 由于人类眼睛的特殊生理结构，如果所看画面之帧率高于16的时候，就会认为是连贯的，此现象称之为视觉暂留。并且当帧速达到一定数值后，再增长的话，人眼也不容易察觉到有明显的流畅度提升了。
- 分辨率：(矩形)图片的长度和宽度，即图片的尺寸
- 压缩前的每秒数据量:帧率X分辨率(单位应该是若干个字节)
- 压缩比:压缩前的每秒数据量/码率 （对于同一个视频源并采用同一种视频编码算法，则：压缩比越高，画面质量越差。）
- 视频文件格式：文件的后缀，比如.wmv,.mov,.mp4,.mp3,.avi,
    * 主要用处，根据文件格式，系统会自动判断用什么软件打开,
注意: 随意修改文件格式，对文件的本身不会造成太大的影响，比如把avi改成mp4,文件还是avi.
- 视频封装格式：一种储存视频信息的容器，流式封装可以有TS、FLV等，索引式的封装有MP4,MOV,AVI等，
    * 主要作用：一个视频文件往往会包含图像和音频，还有一些配置信息(如图像和音频的关联，如何解码它们等)：这些内容需要按照一定的规则组织、封装起来.
    * 注意：会发现封装格式跟文件格式一样，因为一般视频文件格式的后缀名即采用相应的视频封装格式的名称,所以视频文件格式就是视频封装格式。
- 视频封装格式和视频压缩编码标准：就好像项目工程和编程语言，封装格式就是一个项目的工程，视频编码方式就是编程语言，一个项目工程可以用不同语言开发。

#### 直播基础知识介绍
##### 1.采集视频、音频
- 采集视频、音频编码框架
    * AVFoundation:AVFoundation是用来播放和创建实时的视听媒体数据的框架，同时提供Objective-C接口来操作这些视听数据，比如编辑，旋转，重编码
- 视频、音频硬件设备
    * CCD:图像传感器： 用于图像采集和处理的过程，把图像转换成电信号。
    * 拾音器:声音传感器： 用于声音采集和处理的过程，把声音转换成电信号。
    * 音频采样数据:一般都是PCM格式
    * 视频采样数据: 一般都是YUV,或RGB格式，采集到的原始音视频的体积是非常大的，需要经过压缩技术处理来提高传输效率

##### 2.视频处理（美颜，水印）
    * 视频处理原理:因为视频最终也是通过GPU，一帧一帧渲染到屏幕上的，所以我们可以利用OpenGL ES，对视频帧进行各种加工，从而视频各种不同的效果，就好像一个水龙头流出的水，经过若干节管道，然后流向不同的目标
    * 现在的各种美颜和视频添加特效的app都是利用GPUImage这个框架实现的
- 视频处理框架
    * GPUImage : GPUImage是一个基于OpenGL ES的一个强大的图像/视频处理框架,封装好了各种滤镜同时也可以编写自定义的滤镜,其本身内置了多达120多种常见的滤镜效果。
    * OpenGL:OpenGL（全写Open Graphics Library）是个定义了一个跨编程语言、跨平台的编程接口的规格，它用于三维图象（二维的亦可）。OpenGL是个专业的图形程序接口，是一个功能强大，调用方便的底层图形库。
    * OpenGL ES:OpenGL ES (OpenGL for Embedded Systems) 是 OpenGL三维图形 API 的子集，针对手机、PDA和游戏主机等嵌入式设备而设计。

##### 3.视频编码解码
- 视频编码框架
    * FFmpeg:是一个跨平台的开源视频框架,能实现如视频编码,解码,转码,串流,播放等丰富的功能。其支持的视频格式以及播放协议非常丰富,几乎包含了所有音视频编解码、封装格式以及播放协议。
        * -Libswresample:可以对音频进行重采样,rematrixing 以及转换采样格式等操 作。
        * -Libavcodec:提供了一个通用的编解码框架,包含了许多视频,音频,字幕流 等编码/解码器。
        * -Libavformat:用于对视频进行封装/解封装。
        * -Libavutil:包含一些共用的函数,如随机数生成,数据结构,数学运算等。
        * -Libpostproc:用于进行视频的一些后期处理。
        * -Libswscale:用于视频图像缩放,颜色空间转换等。
        * -Libavfilter:提供滤镜功能。
    * X264:把视频原数据YUV编码压缩成H.264格式
    * VideoToolbox:苹果自带的视频硬解码和硬编码API，但是在iOS8之后才开放。
    * AudioToolbox:苹果自带的音频硬解码和硬编码API
- 视频编码技术
    * 视频压缩编码标准：对视频进行压缩(视频编码)或者解压缩（视频解码）的编码技术,比如MPEG，H.264,这些视频编码技术是压缩编码视频的
        * 主要作用:是将视频像素数据压缩成为视频码流，从而降低视频的数据量。如果视频不经过压缩编码的话，体积通常是非常大的，一部电影可能就要上百G的空间。
        * 注意:最影响视频质量的是其视频编码数据和音频编码数据，跟封装格式没有多大关系
    * MPEG:一种视频压缩方式，它采用了帧间压缩，仅存储连续帧之间有差别的地方 ，从而达到较大的压缩比
    * H.264/AVC:一种视频压缩方式,采用事先预测和与MPEG中的P-B帧一样的帧预测方法压缩，它可以根据需要产生适合网络情况传输的视频流,还有更高的压缩比，有更好的图象质量
        * 注意1:如果是从单个画面清晰度比较，MPEG4有优势；从动作连贯性上的清晰度，H.264有优势
        * 注意2:由于264的算法更加复杂，程序实现烦琐，运行它需要更多的处理器和内存资源。因此，运行264对系统要求是比较高的。
        * 注意3:由于264的实现更加灵活，它把一些实现留给了厂商自己去实现，虽然这样给实现带来了很多好处，但是不同产品之间互通成了很大的问题，造成了通过A公司的编码器编出的数据，必须通过A公司的解码器去解这样尴尬的事情
    * H.265/HEVC:一种视频压缩方式,基于H.264，保留原来的某些技术，同时对一些相关的技术加以改进，以改善码流、编码质量、延时和算法复杂度之间的关系，达到最优化设置。
        * H.265 是一种更为高效的编码标准，能够在同等画质效果下将内容的体积压缩得更小，传输时更快更省带宽
        * I帧:(关键帧)保留一副完整的画面，解码时只需要本帧数据就可以完成（因为包含完整画面）
    * P帧:(差别帧)保留这一帧跟之前帧的差别，解码时需要用之前缓存的画面叠加上本帧定义的差别，生成最终画面。（P帧没有完整画面数据，只有与前一帧的画面差别的数据）
    * B帧:(双向差别帧)保留的是本帧与前后帧的差别，解码B帧，不仅要取得之前的缓存画面，还要解码之后的画面，通过前后画面的与本帧数据的叠加取得最终的画面。B帧压缩率高，但是解码时CPU会比较累
    * 帧内（Intraframe）压缩:当压缩一帧图像时，仅考虑本帧的数据而不考虑相邻帧之间的冗余信息,帧内一般采用有损压缩算法
    * 帧间（Interframe）压缩:时间压缩（Temporal compression），它通过比较时间轴上不同帧之间的数据进行压缩。帧间压缩一般是无损的
    * muxing（合成）：将视频流、音频流甚至是字幕流封装到一个文件中(容器格式（FLV，TS）)，作为一个信号进行传输。
- 音频编码技术
    * AAC，mp3：这些属于音频编码技术,压缩音频用
- 码率控制 
    * 多码率:观众所处的网络情况是非常复杂的，有可能是WiFi，有可能4G、3G、甚至2G，那么怎么满足多方需求呢？多搞几条线路，根据当前网络环境自定义码率。
    * 列如：常常看见视频播放软件中的1024，720，高清，标清，流畅等，指的就是各种码率。
- 视频封装格式
    * TS : 一种流媒体封装格式，流媒体封装有一个好处，就是不需要加载索引再播放，大大减少了首次载入的延迟，如果片子比较长，mp4文件的索引相当大，影响用户体验
        * 为什么要用TS:这是因为两个TS片段可以无缝拼接，播放器能连续播放
    * FLV: 一种流媒体封装格式,由于它形成的文件极小、加载速度极快，使得网络观看视频文件成为可能,因此FLV格式成为了当今主流视频格式

##### 4.推流
- 数据传输框架
    * librtmp:用来传输RTMP协议格式的数据
- 流媒体数据传输协议
    * RTMP:实时消息传输协议,Adobe Systems公司为Flash播放器和服务器之间音频、视频和数据传输开发的开放协议，因为是开放协议所以都可以使用了。
        * RTMP协议用于对象、视频、音频的传输。
        * 这个协议建立在TCP协议或者轮询HTTP协议之上。
        * RTMP协议就像一个用来装数据包的容器，这些数据可以是FLV中的视音频数据。一个单一的连接可以通过不同的通道传输多路网络流，这些通道中的包都是按照固定大小的包传输的
    * chunk:消息包

##### 流媒体服务器
- 常用服务器
    * SRS：一款国人开发的优秀开源流媒体服务器系统
    * BMS:也是一款流媒体服务器系统，但不开源，是SRS的商业版，比SRS功能更多
    * nginx:免费开源web服务器，常用来配置流媒体服务器。
- 数据分发
    * CDN：(Content Delivery Network)，即内容分发网络,将网站的内容发布到最接近用户的网络”边缘”，使用户可以就近取得所需的内容，解决 Internet网络拥挤的状况，提高用户访问网站的响应速度.
        * CDN：代理服务器，相当于一个中介。
        * CDN工作原理：比如请求流媒体数据
            * 1.上传流媒体数据到服务器（源站）
            * 2.源站存储流媒体数据
            * 3.客户端播放流媒体，向CDN请求编码后的流媒体数据
            * 4.CDN的服务器响应请求，若节点上没有该流媒体数据存在，则向源站继续请求流媒体数据；若节点上已经缓存了该视频文件，则跳到第6步。
            * 5.源站响应CDN的请求，将流媒体分发到相应的CDN节点上
            * 6.CDN将流媒体数据发送到客户端
    * 回源：当有用户访问某一个URL的时候，如果被解析到的那个CDN节点没有缓存响应的内容，或者是缓存已经到期，就会回源站去获取搜索。如果没有人访问，那么CDN节点不会主动去源站拿.
    * 带宽:在固定的时间可传输的数据总量
        * 比如64位、800MHz的前端总线，它的数据传输率就等于64bit×800MHz÷8(Byte)=6.4GB/s
    * 负载均衡: 由多台服务器以对称的方式组成一个服务器集合，每台服务器都具有等价的地位，都可以单独对外提供服务而无须其他服务器的辅助.
        * 通过某种负载分担技术，将外部发送来的请求均匀分配到对称结构中的某一台服务器上，而接收到请求的服务器独立地回应客户的请求。
        * 均衡负载能够平均分配客户请求到服务器列阵，籍此提供快速获取重要数据，解决大量并发访问服务问题。
        * 这种群集技术可以用最少的投资获得接近于大型主机的性能。
    * QoS（带宽管理）:限制每一个组群的带宽，让有限的带宽发挥最大的效用

##### 拉流
- 直播协议选择：
    * 即时性要求较高或有互动需求的可以采用RTMP,RTSP
    * 对于有回放或跨平台需求的，推荐使用HLS
    * `直播协议对比`    :

![image](https://upload-images.jianshu.io/upload_images/304825-f92e85515845e107.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200)

- HLS:由Apple公司定义的用于实时流传输的协议,HLS基于HTTP协议实现，传输内容包括两部分，一是M3U8描述文件，二是TS媒体文件。可实现流媒体的直播和点播，主要应用在iOS系统
    * HLS是以点播的技术方式来实现直播
    * HLS是自适应码率流播，客户端会根据网络状况自动选择不同码率的视频流，条件允许的情况下使用高码率，网络繁忙的时候使用低码率，并且自动在二者间随意切
换。这对移动设备网络状况不稳定的情况下保障流畅播放非常有帮助。
    * 实现方法是服务器端提供多码率视频流，并且在列表文件中注明，播放器根据播放进度和下载速度自动调整。
- HLS与RTMP对比:HLS主要是延时比较大，RTMP主要优势在于延时低
    * HLS协议的小切片方式会生成大量的文件，存储或处理这些文件会造成大量资源浪费
    * 相比使用RTSP协议的好处在于，一旦切分完成，之后的分发过程完全不需要额外使用任何专门软件，普通的网络服务器即可，大大降低了CDN边缘服务器的配置要求，可以使用任何现成的CDN,而一般服务器很少支持RTSP。
- HTTP-FLV:基于HTTP协议流式的传输媒体内容。
    * 相对于RTMP，HTTP更简单和广为人知，内容延迟同样可以做到1~3秒，打开速度更快，因为HTTP本身没有复杂的状态交互。所以从延迟角度来看，HTTP-FLV要优于RTMP。
- RTSP:实时流传输协议,定义了一对多应用程序如何有效地通过IP网络传送多媒体数据.
- RTP:实时传输协议,RTP是建立在UDP协议上的，常与RTCP一起使用，其本身并没有提供按时发送机制或其它服务质量（QoS）保证，它依赖于低层服务去实现这一过程。
- RTCP:RTP的配套协议,主要功能是为RTP所提供的服务质量（QoS）提供反馈，收集相关媒体连接的统计信息，例如传输字节数，传输分组数，丢失分组数，单向和双向网络延迟等等。

##### 解码
- 解封装
    * demuxing（分离）：从视频流、音频流，字幕流合成的文件(容器格式（FLV，TS）)中， 分解出视频、音频或字幕，各自进行解码。
- 音频编码框架
    * fdk_aac:音频编码解码框架，PCM音频数据和AAC音频数据互转
- 解码介绍
    * 硬解码：用GPU来解码，减少CPU运算
        * 优点：播放流畅、低功耗，解码速度快，
        * 缺点：兼容不好
    * 软解码：用CPU来解码
        * 优点：兼容好
        * 缺点：加大CPU负担，耗电增加、没有硬解码流畅，解码速度相对慢

##### 播放
- ijkplayer:一个基于FFmpeg的开源Android/iOS视频播放器
    * API易于集成；
    * 编译配置可裁剪，方便控制安装包大小；
    * 支持硬件加速解码，更加省电
    * 简单易用，指定拉流URL，自动解码播放.

##### 聊天互动
- IM:(InstantMessaging)即时通讯:是一个实时通信系统，允许两人或多人使用网络实时的传递文字消息、文件、语音与视频交流.
    * IM在直播系统中的主要作用是实现观众与主播、观众与观众之间的文字互动.
- 腾讯云：腾讯提供的即时通讯SDK，可作为直播的聊天室
- 融云：一个比较常用的即时通讯SDK，可作为直播的聊天室

####  








## 图像处理
### 1.图像的压缩、解压。
### 2.一张物理体积20KB、分辨率为 200 * 300 的图片，在内存中占用多大的空间？
### 3.GLSurfaceView的相关知识，OpenGL，Shader，绘制流程。


## iOS 动画
### 1.简要说一下常用的动画库。
### 2.请说一下对 CALayer 的认识。
### 3.解释一下 CALayer.contents 属性。
### 4.在 iOS 中，动画有哪几种类型？
- CABasicAnimation基本动画（fromValue和toValue）
- CAKeyframeAnimation关键帧动画
- UIView 动画
    * layer的CATransform3DIdentity;
    * view的CGAffineTransformIdentity；

### 5.隐式动画
### 6.显式动画

## 蓝牙

## ARKit

## Core ML


## 代码管理、持续集成、项目托管
### 1.Git
#### 1.`git pull` 和 `git fetch` 的区别？
#### 2.`git merge` 和 `git rebase` 的区别？
#### 3.如何在本地新建一个分支，并 push 到远程服务器上？
#### 4.如果 fork 了一个别人的仓库，怎样与源仓库保持同步
#### 5.总结一下 Git 常用的命令？
### 2.Svn
### 3.CocoaPods
#### 1.说一下 `CocoaPods` 的原理？
#### 2.如何让自己写的框架支持 `CocoaPods`？
#### 3.`pod update` 和 `pod install` 有什么区别？
#### 4.`Podfile.lock` 文件起什么作用？
#### 5.CocoaPods 常用指令？
#### 6.在使用 CocoaPods 中遇到过哪些问题？
#### 7.如何使用 CocoaPods 集成远程私有库？
#### 8.如果自己写的库需要依赖其他的三方库，该怎么办？
#### 9.CocoaPods 中的 Subspec 字段有什么用处？
### 4.Carthage
### 5.Fastlane
### 6.Jenkins
### 7.fir.im
### 8.蒲公英
### 9.TestFlight


## 数据安全及加密
### 1.RSA非对称加密  
### 2.AES对称加密
### 3.DES加密
### 4.Base64加密
- base64 编码是现代密码学的基础
- 基本原理：
    * 原本是 8个bit 一组表示数据,改为 6个bit一组表示数据,不足的部分补零,每 两个0 用 一个 = 表示
- 用base64 编码之后,数据长度会变大,增加了大约 1/3 左右.(8-6)/6
- 可进行反向解密
- Xcode7.0 之后出现的
- 编码有个非常显著的特点,末尾有个 = 号
- 将文件进行加密

```
// 获取需要加密文件的二进制数据
NSData *data = [NSData dataWithContentsOfFile:@"/Users/wangpengfei/Desktop/photo/IMG_5551.jpg"];
// 或 base64EncodedStringWithOptions
NSData *base64Data = [data base64EncodedDataWithOptions:0];
// 将加密后的文件存储到桌面
[base64Data writeToFile:@"/Users/wangpengfei/Desktop/123" atomically:YES];
```
- 将文件进行解密

```
// 获得加密后的二进制数据
NSData *base64Data = [NSData dataWithContentsOfFile:@"/Users/wangpengfei/Desktop/123"];
// 解密 base64 数据
NSData *baseData = [[NSData alloc] initWithBase64EncodedData:base64Data options:0];
// 写入桌面
[baseData writeToFile:@"/Users/wangpengfei/Desktop/IMG_5551.jpg" atomically:YES];
```
- 利用终端命令进行base64运算:

```
// 将文件 meinv.jpg 进行 base64运算之后存储为 meinv.txt
base64 meinv.jpg -o meinv.txt
// 讲meinv.txt 解码生成 meinv.png
base64 -D meinv.txt -o meinv.png
// 将字符串 "hello" 进行 base 64 编码 结果:aGVsbG8=cho "hello" | base64
// 将 base64编码之后的结果 aGVsbG8= 反编码为字符串
echo aGVsbG8= | base64 -D
```

### 5.MD5加密
- 把一个任意长度的字节串变换成一定长度的十六进制的大整数.
- 注意,字符串的转换过程是不可逆的,不能通过加密结果,反向推导出原始内容
- 需要导入第三方框架: NSString+Hash
- MD5特点:
    * 压缩性 : 任意长度的数据,算出的 MD5 值长度都是固定的.
    * 容易计算 : 从原数据计算出 MD5 值很容易.
    * 抗修改性 : 对原数据进行任何改动,哪怕只修改一个字节,所得到的 MD5 值都有很大区别.
    * 弱抗碰撞 : 已知原数据和其 MD5 值,想找到一个具有相同 MD5 值的数据(即伪造数据)是非常困难的.
    * 强抗碰撞: 想找到两个不同数据,使他们具有相同的 MD5 值,是非常困难的
- MD5 应用:
    * 一致性验证:MD5将整个文件当做一个大文本信息,通过不可逆的字符串变换算法,产生一个唯一的MD5信息摘要.就像每个人都有自己独一无二的指纹,MD5对任何文件产生一个独一无二的数字指纹.
    * 利用 MD5 来进行文件校验,被大量应用在软件下载站,论坛数据库,系统文件安全等方面(是否认为添加木马，篡改文件内容等).百度‘MD5'第一个网站进去，利用数据库伪解密,即反查询
    * 数字签名;
    * 安全访问认证;

### 6.简述 `SSL` 加密的过程用了哪些加密方法，为何这么作？
### 7.是否了解 `iOS` 的签名机制？
### 8.如何对 `APP` 进行重签名？
### 9.在HTTPS建立连接的时候都用了哪些加密算法，为什么要这么设计
### 10.常见的加密算法
- iOS Base64编码
- 哈希(散列)函数(消息摘要算法）：MD5、SHA、HMAC
- 对称加密算法：DES、3DES、AES、RC4
- 非对称加密算法：RSA
- 苹果钥匙链Keychain

![image](https://upload-images.jianshu.io/upload_images/2000534-492cd6051748c9ab.png?imageMogr2/auto-orient/strip|imageView2/2/w/946)

### 补充：常见的加密方式
- base64加密
- POST加密
- Token值
- MD5加密
- 时间戳密码
- 钥匙串访问
- 指纹识别

### 11.对称加密算法和非对称加密算法的区别


## 源代码阅读
### 1.YYKit
### 2.SDWebImage
#### 面试常见问题
#### 1.看过sdwebimage的源码吗？说一下sdwebimage的原理
- SDWebImage加载图片的流程
    * 入口 setImageWithURL:placeholderImage:options:会先把 placeholderImage显示，然后 SDWebImageManager根据 URL 开始处理图片。
    * 进入SDWebImageManager类中downloadWithURL:delegate:options:userInfo:，交给 SDImageCache从缓存查找图片是否已经下载 queryDiskCacheForKey:delegate:userInfo:.
    * 先从内存图片缓存查找是否有图片，如果内存中已经有图片缓存，SDImageCacheDelegate回调 imageCache:didFindImage:forKey:userInfo:到 SDWebImageManager。
    * SDWebImageManagerDelegate 回调 webImageManager:didFinishWithImage: 到 UIImageView+WebCache,等前端展示图片。
    * 如果内存缓存中没有，生成 ｀NSOperation ｀ 添加到队列，开始从硬盘查找图片是否已经缓存。
    * 根据 URL的MD5值Key在硬盘缓存目录下尝试读取图片文件。这一步是在 NSOperation 进行的操作，所以回主线程进行结果回调 notifyDelegate:。
    * 如果上一操作从硬盘读取到了图片，将图片添加到内存缓存中（如果空闲内存过小， 会先清空内存缓存）。SDImageCacheDelegate'回调 imageCache:didFindImage:forKey:userInfo:`。进而回调展示图片。
    * 如果从硬盘缓存目录读取不到图片，说明所有缓存都不存在该图片，需要下载图片， 回调 imageCache:didNotFindImageForKey:userInfo:。
    * 共享或重新生成一个下载器 SDWebImageDownloader开始下载图片。
    * 图片下载由 NSURLConnection来做，实现相关 delegate 来判断图片下载中、下载完成和下载失败。
    * connection:didReceiveData: 中利用 ImageIO做了按图片下载进度加载效果。
    * connectionDidFinishLoading: 数据下载完成后交给 SDWebImageDecoder做图片解码处理。
    * 图片解码处理在一个 NSOperationQueue完成，不会拖慢主线程 UI.如果有需要 对下载的图片进行二次处理，最好也在这里完成，效率会好很多。
    * 在主线程 notifyDelegateOnMainThreadWithInfo: 宣告解码完成 imageDecoder:didFinishDecodingImage:userInfo: 回调给 SDWebImageDownloader`。
    * imageDownloader:didFinishWithImage:回调给 SDWebImageManager告知图片 下载完成。
    * 通知所有的 downloadDelegates下载完成，回调给需要的地方展示图片。
    * 将图片保存到 SDImageCache中，内存缓存和硬盘缓存同时保存。写文件到硬盘 也在以单独 NSOperation 完成，避免拖慢主线程。
    * SDImageCache 在初始化的时候会注册一些消息通知， 在内存警告或退到后台的时 候清理内存图片缓存，应用结束的时候清理过期图片。
#### 2.说一下SDWebImage的缓存策略？
- 有一个专门的 Cache 分类用来处理图片的缓存。 这里面也有两个类 SDImageCache 和 SDImageCacheConfig。 大部分的缓存处理都在 SDImageCache 这个类中实现。
- SDImageCache 中有一个叫做 memCache 的属性，它是一个 NSCache 对象，用于实现我们对图片的 Memory Cache，其实就是接受系统的内存警告通知，然后清除掉自身的图片缓存。Disk Cache，也就是文件缓存，SDWebImage 会将图片存放到 NSCachesDirectory目录中，然后为每一个缓存文件生成一个 md5 文件名, 存放到文件中。
- Memory 和 Disk 双缓存
    * Memory(内存)中查找：SDImageCache 类的 queryDiskCacheForKey方法，查询图片缓存，queryDiskCacheForKey 方法内部， 先会查询 Memory Cache ，如果查找到就直接返回，反之进入下面的硬盘查找。
    * Disk(硬盘) 中查找：如果 Memory Cache查找不到， 就会查询 Disk Cache，查询Disk Cache 的时候有一个小插曲，就是如果 Disk Cache 查询成功，还会把得到的图片再次设置到 Memory Cache 中。这样做可以最大化那些高频率展现图片的效率。如果找不到就进入下面的网络下载。
    * 网路下载：请求网络使用的是imageDownloader属性，这个示例专门负责下载图片数据。如果下载失败， 会把失败的图片地址写入failedURLs集合，为什么要有这个 failedURLs 呢，因为SDWebImage默认会有一个对上次加载失败的图片拒绝再次加载的机制。也就是说，一张图片在本次会话加载失败了，如果再次加载就会直接拒绝，SDWebImage这样做可能是为了提高性能。如果下载图片成功了，接下来就会使用 [self.imageCache storeImage]方法将它写入缓存，同时也会写入硬盘，并且调用 completedBlock 告诉前端显示图片。
    * Disk(硬盘)缓存清理策略：SDWebImage 会在每次 APP 结束的时候执行清理任务。清理缓存的规则分两步进行。第一步先清除掉过期的缓存文件。如果清除掉过期的缓存之后，空间还不够。那么就继续按文件时间从早到晚排序，先清除最早的缓存文件，直到剩余空间达到要求。

#### 补充：如何设计一个图片缓存框架？
- 可以模仿 SDWebImage 来实现。
- 构成
    * Manager
    * 内存缓存
    * 磁盘缓存
    * 网络下载
    * Code Manager
        * 图片解码
        * 图片解压缩
        * 图片的存储是以图片的单向 hash 值为 Key
- 内存设计需要考虑的问题
    * 存储的 Size
        * 因为内存的空间有限，我们针对不同尺寸的图片，给出不同的方案
        * 10K 以下的50个
        * 100Kb 以下的20个
        * 100kb 以上的10个
    * 淘汰的策略
        * 内存的淘汰策略采取LRU（最近最少使用算法）
        * 触发淘汰策略的时机有三种
            * 定期检查（不建议，耗性能）
            * 提高检查触发频率（一定要注意开销）
                * 前后台切换的时候
                * 每次读写的时候
- 磁盘设计需要考虑的问题
    * 存储方式
    * 大小限制（有固定的大小）
    * 移除策略（可以设置为7天或者15天）
- 网络设计需要考虑的问题
    * 图片请求的最大并发量
    * 请求超时策略
    * 请求优先级
- 图片解码
    * 应用 策略模式，针对 jpg、png、gif 等不同的图片格式进行解码
    * 图片解码的时机
        * 在 子线程 图片刚下载完时
        * 在 子线程 刚从磁盘读取完时
        * 避免在主线程解压缩、解码，避免卡顿

#### 3.磁盘缓存时间，默认的缓存路径，怎么处理图片的名称?默认的超时时间是多少?最大并发数？
#### 4.该框架内部对内存警告的处理方式?（或者问：当app接收到内存警告时，SDWebImage做了什么？）
#### 5.NSCache和字典的区别？
#### 6.如何计算图片的成本?
#### 7.保证错误的URL不会被尝试重新下载，使用什么来下载图片的 
#### 8.sdwebimage是一个异步下载图片的三方，怎么保证线程安全的？
#### 9.如果一个页面 加载图片很卡 ，什么原因，会跟sdwebimage有关吗，还是跟图片渲染有关？
#### 10.如果收到内存警告怎么办
- 如果使用了SDWebImage框架,使用如下代码,可以有效的减少内存:

```
[[SDImageCache sharedImageCache] setValue:nil forKey:@"memCache"];//清除内存中通过SDWebImage框架下载的图片,建议在收到内存警告时在调用
```
#### 11.SDWebImage是如何做到Url不变的情况下，更新图片内容的？
- SDWebImage它是基于URL作为Key来实现图片缓存机制的。大多数情况下，片与URL是一一对应的，即使服务器修改了图片也会相应的变更URL。但是在少数情况下，服务器修改了图片后不会变更相应的URL，也就是说图片本身的内容变了然而它的URL没有变化，那么按照对SDWebImage的常规使用方法的话，客户端肯定更新不到同一URL对应到服务器已变更的图片内容。
- 客户端第一次请求图片时，Charles抓包得知response header里有一个名为Last-Modified、数据是时间戳的键值对。
- 客户端第二次及以后请求图片时，通过Charles抓包发现，服务器返回304 not modified状态，说明服务器在接收客户端请求后通过某种判断逻辑得出结论：“客户端已缓存的图片与服务器图片都是最新的”，那么服务器如何判断的呢？
- 通过查阅HTTP协议相关的资料得知，与服务器返回的Last-Modified相对应的request header里可以加一个名为If-Modified-Since的key，value即是服务器回传的服务端图片最后被修改的时间，第一次图片请求时If-Modified-Since的值为空，第二次及以后的客户端请求会把服务器回传的Last-Modified值作为If-Modified-Since的值传给服务器，这样服务器每次接收到图片请求时就将If-Modified-Since与Last-Modified进行比较，如果客户端图片已陈旧那么返回状态码200、Last-Modified、图片内容，客户端存储Last-Modified和图片；如果客户端图片是最新的那么返回304 Not Modified、不会返回Last-Modified、图片内容。
- Apache比较时是看If-Modified-Since之后有没有更新图片，Nginx比较时是看If-Modified-Since与Last-Modified是否相等，所以对于Apache服务器环境客户端每次都要严格的存储服务器回传的Last-Modified以便下次请求时作为If-Modified-Since的值传给服务器，对于Nginx服务器环境客户端不必存储服务器回传的Last-Modified，每次请求时只需将图片自身的fileModificationDate作为If-Modified-Since的值传服务器即可。在实际开发中，如果遇到明明传了If-Modified-Since、服务器图片也变更了、但是客户端却请求不到最新的图片的情况时，那么就需要查看一下服务器对这两个时间戳的比较逻辑。
- 那么，现在我们可以回到SDWebImage上来了。通过查看SDWebImageDownloader的源码得知，它开放了一个headersFilter的block，意在让开发者可以对所有图片请求追加一些额外的header，这正合我意。那么我们就可以在诸如AppDelegate didFinishLaunching的地方追加如下代码：

```
SDWebImageDownloader *imgDownloader = SDWebImageManager.sharedManager.imageDownloader;
imgDownloader.headersFilter  = ^NSDictionary *(NSURL *url, NSDictionary *headers) {

    NSFileManager *fm = [[NSFileManager alloc] init];
    NSString *imgKey = [SDWebImageManager.sharedManager cacheKeyForURL:url];
    NSString *imgPath = [SDWebImageManager.sharedManager.imageCache defaultCachePathForKey:imgKey];
    NSDictionary *fileAttr = [fm attributesOfItemAtPath:imgPath error:nil];

    NSMutableDictionary *mutableHeaders = [headers mutableCopy];

    NSDate *lastModifiedDate = nil;

    if (fileAttr.count > 0) {
        if (fileAttr.count > 0) {
            lastModifiedDate = (NSDate *)fileAttr[NSFileModificationDate];
        }

    }
    NSDateFormatter *formatter = [[NSDateFormatter alloc] init];
    formatter.timeZone = [NSTimeZone timeZoneWithAbbreviation:@"GMT"];
    formatter.locale = [[NSLocale alloc] initWithLocaleIdentifier:@"en_US"];
    formatter.dateFormat = @"EEE, dd MMM yyyy HH:mm:ss z";

    NSString *lastModifiedStr = [formatter stringFromDate:lastModifiedDate];
    lastModifiedStr = lastModifiedStr.length > 0 ? lastModifiedStr : @"";
    [mutableHeaders setValue:lastModifiedStr forKey:@"If-Modified-Since"];

    return mutableHeaders;
};

```
- 然后，加载图片的地方以前怎么写还是怎么写，但别忘了Option是SDWebImageRefreshCached

```
NSURL *imgURL = [NSURL URLWithString:@"http://handy-img-storage.b0.upaiyun.com/3.jpg"];  
[[self imageView] sd_setImageWithURL:imgURL  
                    placeholderImage:nil  
                             options:SDWebImageRefreshCached];
                             
```
- 经测试，服务器只修改图片不变更URL的时候，客户端也可以更新到最新的图片。
从以上第一段代码内容可以看出我采用的是与ngix服务器比较逻辑对应的代码，BTW:我测试的服务器是又拍云，说明又拍云的比较逻辑是等与不等的关系判断，不是大小关系的判断。
- 这里顺便说一下，如果服务器的环境是类似于Apache的比较逻辑时，客户端可以把Last-Modified存放在图片的名称上(这需要修改SDWebImage源码，不建议)，或者用一个plist文件存放图片key名称与时间的对应关系(这个不用修改源码)。
- OK，到此这次的主题已得到完美解决。
- 其实，在抓取服务器返回的数据包时，还发现response header中还有一个ETag，与之相对应的request header中可以追加一个If-None-Match的key，这对header与Last-Modified、If-Modified-Since的作用是相同的，即服务器是否需要返回最新的图片，当然它们在服务器端的判断逻辑应该是等与不等的判断，Etag在客户端的存储同样可以采用在plist文件中存放图片key名称与Etag的对应关系。

### 3.AFNetworking
### 4.SVProgressHub 
### 5.Texture（ASDK）


## iOS逆向及安全
### 1.怎么防止反编译？
- 本地数据加密。
    * iOS应用防反编译加密技术之一：对NSUserDefaults，sqlite存储文件数据加密，保护帐号和关键信息
- URL编码加密。
    * iOS应用防反编译加密技术之二：对程序中出现的URL进行编码加密，防止URL被静态分析
- 网络传输数据加密。
    * iOS应用防反编译加密技术之三：对客户端传输数据提供加密方案，有效防止通过网络接口的拦截获取数据
- 方法体，方法名高级混淆。
    * iOS应用防反编译加密技术之四：对应用程序的方法名和方法体进行混淆，保证源码被逆向后无法解析代码
- 程序结构混排加密。
    * iOS应用防反编译加密技术之五：对应用程序逻辑结构进行打乱混排，保证源码可读性降到最低

### 2.项目中网络层如何做安全处理？
- 尽量使用https
    * https可以过滤掉大部分的安全问题。https在证书申请，服务器配置，性能优化，客户端配置上都需要投入精力，所以缺乏安全意识的开发人员容易跳过https，或者拖到以后遇到问题再优化。https除了性能优化麻烦一些以外其他都比想象中的简单，如果没精力优化性能，至少在注册登录模块需要启用https，这部分业务对性能要求比较低。
- 不要传输明文密码
    * 不知道现在还有多少app后台是明文存储密码的。无论客户端，server还是网络传输都要避免明文密码，要使用hash值。客户端不要做任何密码相关的存储，hash值也不行。存储token进行下一次的认证，而且token需要设置有效期，使用refresh，token去申请新的token。
- Post并不比Get安全
    * 事实上，Post和Get一样不安全，都是明文。参数放在QueryString或者Body没任何安全上的差别。在Http的环境下，使用Post或者Get都需要做加密和签名处理。
- 不要使用301跳转
    * 301跳转很容易被Http劫持攻击。移动端http使用301比桌面端更危险，用户看不到浏览器地址，无法察觉到被重定向到了其他地址。如果一定要使用，确保跳转发生在https的环境下，而且https做了证书绑定校验。
- http请求都带上MAC
    * 所有客户端发出的请求，无论是查询还是写操作，都带上MAC（Message Authentication Code）。MAC不但能保证请求没有被篡改（Integrity），还能保证请求确实来自你的合法客户端（Signing）。当然前提是你客户端的key没有被泄漏，如何保证客户端key的安全是另一个话题。MAC值的计算可以简单的处理为hash（request params＋key）。带上MAC之后，服务器就可以过滤掉绝大部分的非法请求。MAC虽然带有签名的功能，和RSA证书的电子签名方式却不一样，原因是MAC签名和签名验证使用的是同一个key，而RSA是使用私钥签名，公钥验证，MAC的签名并不具备法律效应。
- http请求使用临时密钥
    * 高延迟的网络环境下，不经优化https的体验确实会明显不如http。在不具备https条件或对网络性能要求较高且缺乏https优化经验的场景下，http的流量也应该使用AES进行加密。AES的密钥可以由客户端来临时生成，不过这个临时的AES key需要使用服务器的公钥进行加密，确保只有自己的服务器才能解开这个请求的信息，当然服务器的response也需要使用同样的AES key进行加密。由于http的应用场景都是由客户端发起，服务器响应，所以这种由客户端单方生成密钥的方式可以一定程度上便捷的保证通信安全。
- AES使用CBC模式
    * 不要使用ECB模式，记得设置初始化向量，每个block加密之前要和上个block的秘文进行运算。


## Coretext
## 项目组件化
### 1.说一下你之前项目的组件化方案？
### 2.项目的组件化模块应该如何划分？
### 3.如何集成本地私有库？
### 4.如何集成远程私有库？


## 性能优化
### 1.如何提升 `tableview` 的流畅度？
- 本质上是降低 CPU、GPU 的工作，从这两个大的方面去提升性能。
    * CPU：对象的创建和销毁、对象属性的调整、布局计算、文本的计算和排版、图片的格式转换和解码、图像的绘制
    * GPU：纹理的渲染
- 卡顿优化在 CPU 层面
    * 尽量用轻量级的对象，比如用不到事件处理的地方，可以考虑使用 CALayer 取代 UIView
    * 不要频繁地调用 UIView 的相关属性，比如 frame、bounds、transform 等属性，尽量减少不必要的修改
    * 尽量提前计算好布局，在有需要时一次性调整对应的属性，不要多次修改属性
    * Autolayout 会比直接设置 frame 消耗更多的 CPU 资源
    * 图片的 size 最好刚好跟 UIImageView 的 size 保持一致
    * 控制一下线程的最大并发数量
    * 尽量把耗时的操作放到子线程
        * 文本处理（尺寸计算、绘制）
        * 图片处理（解码、绘制）
- 卡顿优化在 GPU层面
    * 尽量避免短时间内大量图片的显示，尽可能将多张图片合成一张进行显示
    * GPU能处理的最大纹理尺寸是 4096x4096，一旦超过这个尺寸，就会占用 CPU 资源进行处理，所以纹理尽量不要超过这个尺寸
    * 尽量减少视图数量和层次
    * 减少透明的视图（alpha<1），不透明的就设置 opaque 为 YES
    * 尽量避免出现离屏渲染
- iOS 保持界面流畅的技巧
    * 预排版，提前计算
        * 在接收到服务端返回的数据后，尽量将 CoreText 排版的结果、单个控件的高度、cell 整体的高度提前计算好，将其存储在模型的属性中。需要使用时，直接从模型中往外取，避免了计算的过程。
        * 尽量少用 UILabel，可以使用 CALayer 。避免使用AutoLayout的自动布局技术，采取纯代码的方式
    * 预渲染，提前绘制
        * 例如圆形的图标可以提前在，在接收到网络返回数据时，在后台线程进行处理，直接存储在模型数据里，回到主线程后直接调用就可以了，避免使用CALayer的Border、corner、shadow、mask 等技术，这些都会触发离屏渲染。
    * 异步绘制
    * 全局并发线程
    * 高效的图片异步加载

### 2.如何使用 `Instruments` 进行性能调优？(Time Profiler、Zombies、Allocations、Leaks)
### 3.如何优化 `APP` 的启动时间
- App启动过程
    * 解析Info.plist
    * 加载相关信息，例如闪屏
    * 沙箱建立、权限检查
    * Mach-O加载
    * 如果是胖二进制文件，寻找合适当前CPU类别的部分
    * 加载所有依赖的Mach-O文件（递归调用Mach-O加载的方法）
    * 定位内部、外部指针引用，例如字符串、函数等
    * 执行声明为attribute((constructor))的C函数
    * 加载类扩展（Category）中的方法
    * C++静态对象加载、调用ObjC的 +load 函数
    * 程序执行
    * 调用main()
    * 调用UIApplicationMain()
    * 调用applicationWillFinishLaunching
- 影响启动性能的因素
    * main()函数之前耗时的影响因素
        * 动态库加载越多，启动越慢。
        * ObjC类越多，启动越慢
        * C的constructor函数越多，启动越慢
        * C++静态对象越多，启动越慢
        * ObjC的+load越多，启动越慢
    * main()函数之后耗时的影响因素
        * 执行main()函数的耗时
        * 执行applicationWillFinishLaunching的耗时
        * rootViewController及其childViewController的加载、view及其subviews的加载

### 4.今日头条的启动优化方案
- 针对于今日头条这个App我们可以优化的点如下：
    * 纯代码方式而不是storyboard加载首页UI。
    * 对didFinishLaunching里的函数考虑能否挖掘可以延迟加载或者懒加载，需要与各个业务方pm和rd共同check 对于一些已经下线的业务，删减冗余代码。
    * 对于一些与UI展示无关的业务，如微博认证过期检查、图片最大缓存空间设置等做延迟加载。
    * 对实现了+load()方法的类进行分析，尽量将load里的代码延后调用。
    * 上面统计数据显示展示feed的导航控制器页面(NewsListViewController)比较耗时，对于viewDidLoad以及viewWillAppear方法中尽量去尝试少做，晚做，不做。

### 5.如何对 `APP` 进行内存、电量、网络流量的优化
### 6.如何有效降低 `APP` 包的大小？
- 可执行文件
    * 编译器优化
        * Strip Linked Product、Make Strings Read-Only、Symbols Hidden by Default 设置为 YES
        * 去掉异常支持，Enable C++ Exceptions、Enable Objective-C Exceptions 设置为 NO， Other C Flags 添加 -fno-exceptions
    * 利用 AppCode 检测未使用的代码：菜单栏 -> Code -> Inspect Code
    * 编写LLVM插件检测出重复代码、未被调用的代码
- 资源
    * 资源包括 图片、音频、视频 等
    * 优化的方式可以对资源进行无损的压缩
    * 去除没有用到的资源

### 7.日常如何检查内存泄露？
- 目前我知道的方式有以下几种
    * Memory Leaks
    * Alloctions
    * Analyse
    * Debug Memory Graph
    * MLeaksFinder
- 泄露的内存主要有以下两种
    * Laek Memory这种是忘记Release操作所泄露的内存。
    * Abandon Memory这种是循环引用，无法释放掉的内存。

### 8.能不能说一下物理屏幕显示的原理？
- CPU 计算好显示内容提交到 GPU，GPU 渲染完成后将渲染结果放入帧缓冲区，视频控制器收到VSync信号后逐行读取帧缓冲区的数据，再经过一定的数模转换传递给显示器显示。
- iOS屏幕刷新机制
    * 为了解决单缓存区的问题，iOS设备在这个过程中采取了如下图所示的双缓存区+VSync机制：
        * GPU 会预先渲染好一帧放入一个缓存区内（前帧缓存）。
        * 在显示器发出VSync后，视频控制器的指针会指向前帧缓存区并开始读取，GPU开始渲染下一帧，并将渲染结果放入另一个缓存区（后帧缓存）。
        * 在显示器发出新的VSync后，视频控制器的指针会指向后帧缓存区并开始读取，GPU开始渲染下一帧，并将渲染结果放入前帧缓存区。
- 双缓存和VSync造成的问题
    * 每一帧画面要先经过CPU计算，再经过GPU渲染，最后存入缓存区供视频控制器读取。由于垂直同步的机制，如果在一个VSync时间内，CPU 或者 GPU 没有完成内容提交，则那一帧就会被丢弃，而这时显示屏会保留之前的内容不变，也就造成界面卡顿。
- 为了降低双缓存造成界面卡顿的几率，有些设备（如安卓设备）会引入三缓存+VSync机制，但iOS设备一直都是双缓存+垂直同步机制。
- 三缓存区的工作原理同双缓冲类似，只是多了一个 Back Buffer（图中的缓存区C）。三缓存区只是能降低界面卡顿的几率，并不能解决这个问题。

### 9.解释一下什么是屏幕卡顿、掉帧？该如何避免？
- 图像显示相关的原理
    * iOS系统中 CPU、GPU、显示器是以下面图中方式协同工作的。CPU和GPU是通过总线链接起来的，CPU 计算好显示内容提交到 GPU，GPU 渲染完成后将渲染结果放入帧缓冲区，视频控制器会按照 VSync 信号逐行读取帧缓冲区的数据，经过数模转换传递给显示器显示。 
- 关于CPU和GPU的分工又有以下内容：
    * CPU负责：
        * 对象创建和销毁
        * 对象属性调整
        * 布局计算、文本的计算
        * 排版、图片的格式转换和解码
        * 图像的绘制
    * GPU负责：
        * 纹理的渲染
        * 视图的混合
        * 图形的生成
- IOS视图卡顿掉帧的原因
    * 标准情况下，页面滑动流畅是60FPs ，就是每一秒有60帧的画面刷新，每16.7ms(1/60秒)有一帧数据。上图两个VSync 之间的时间就是16.7ms。 如果CPU 和 GPU 加起来的处理时间超过了 16.7ms，就会造成掉帧甚至卡顿。当FPs 帧数低于30时，人的肉眼就能感觉到画面明显的卡顿。
- 如何监控界面的卡顿
    * 思路一：监控一秒钟内的帧数是否经常低于或远低于 60FPs。
    * 思路二：监控每一帧的时长是否超时。
- 思路一实现方法：用 CADisplayLinker 来计数
> CADisplayLink可以以屏幕刷新的频率调用指定selector，iOS系统中正常的屏幕刷新率为60次/秒，只要在这个方法里面统计每秒这个方法执行的次数，通过次数/时间就可以得出当前屏幕的刷新率了。

- 思路二实现方法：通过子线程监测主线程的RunLoop，判断两个状态RunLoop的状态区域之间的耗时是否达到一定阈值。
> 开启子线程,实时计算这两个状态区域之间的耗时是否到达某个阀值,便能揪出这些性能杀手，假定连续6次超时50ms认为卡顿(当然也包含了单次超时300ms)

- 如何优化掉帧卡顿
    * 图像显示的工作是由CPU和GPU协同完成的， 那么优化的方向和思路就是尽量减少他们的处理时长。
    * 对CPU处理的优化:
        * 在子线程中进行对象的创建,调整和销毁，节省一部分CPU的时间
        * 在子线程中预排版(布局计算,文本计算)，让主线程有更多的时间去响应用户的交互
        * 对文本等异步绘制,图片编解码等内容进行 预渲染、预排版
    * 对GPU处理的优化
        * 尽量避免使用 CALayer 的 Border、corner、shadow、mask 等技术，这样能少触发离屏渲染
        * 尽可能将多张图片合成为一张进行显示，减轻视图层级

### 10.什么是`离屏渲染`？什么情况下会触发？该如何应对？
- 离屏渲染就是在当前屏幕缓冲区以外，新开辟一个缓冲区进行操作。
- 离屏渲染出发的场景
    * 圆角 （maskToBounds并用才会触发）
    * 图层蒙版
    * 阴影
    * 光栅化
- 为什么要避免离屏渲染？
    * CPU、GPU在绘制渲染视图时做了大量的工作。离屏渲染发生在GPU层面上，会创建新的渲染缓冲区，会触发 OpenGL的多通道渲染管线，图形上下文的切换会造成额外的开销，增加 GPU 工作量。如果 CPU GPU 累计耗时16.67毫秒还没有完成，就会造成卡顿掉帧。
    * 圆角属性、蒙层遮罩都会触发离屏渲染。指定了以上属性，标记了它在新的图形上下文中，在未愈合之前，不可以用于显示的时候就出发了离屏渲染。
- 在OpenGL中，GPU有2种渲染方式
    * On-Screen Rendering：当前屏幕渲染，在当前用于显示的屏幕缓冲区进行渲染操作
    * Off-Screen Rendering：离屏渲染，在当前屏幕缓冲区以外新开辟一个缓冲区进行渲染操作
- 离屏渲染消耗性能的原因
    * 需要创建新的缓冲区
    * 离屏渲染的整个过程，需要多次切换上下文环境，先是从当前屏幕（On-Screen）切换到离屏（Off-Screen）；等到离屏渲染结束以后，将离屏缓冲区的渲染结果显示到屏幕上，又需要将上下文环境从离屏切换到当前屏幕
- 哪些操作会触发离屏渲染？
    * 光栅化，layer.shouldRasterize = YES
    * 遮罩，layer.mask
    * 圆角，同时设置 layer.masksToBounds = YES、layer.cornerRadius大于0
    * 考虑通过 CoreGraphics 绘制裁剪圆角，或者叫美工提供圆角图片
    * 阴影，layer.shadowXXX，如果设置了 layer.shadowPath 就不会产生离屏渲染；

### 11.如何检测离屏渲染？
- 模拟器debug-选中color Offscreen - Renderd离屏渲染的图层高亮成黄 可能存在性能问题
- 真机Instrument-选中Core Animation-勾选Color Offscreen-Rendered Yellow
- 离屏渲染的触发方式
    * 设置了以下属性时，都会触发离屏绘制：
        * layer.shouldRasterize（光栅化）
            * 光栅化概念：将图转化为一个个栅格组成的图象。
            * 光栅化特点：每个元素对应帧缓冲区中的一像素。
        * masks（遮罩）
        * shadows（阴影）
        * edge antialiasing（抗锯齿）
        * group opacity（不透明）
        * 复杂形状设置圆角等
        * 渐变
        * drawRect
- 例如我们日程经常打交道的TableViewCell,因为TableViewCell的重绘是很频繁的（因为Cell的复用）,如果Cell的内容不断变化,则Cell需要不断重绘,如果此时设置了cell.layer可光栅化。则会造成大量的离屏渲染,降低图形性能。
- 如果将不在GPU的当前屏幕缓冲区中进行的渲染都称为离屏渲染，那么就还有另一种特殊的“离屏渲染”方式：CPU渲染。如果我们重写了drawRect方法，并且使用任何Core Graphics的技术进行了绘制操作，就涉及到了CPU渲染。整个渲染过程由CPU在App内同步地完成，渲染得到的bitmap最后再交由GPU用于显示。
- 现在摆在我们面前得有三个选择：当前屏幕渲染、离屏渲染、CPU渲染，该用哪个呢？这需要根据具体的使用场景来决定。
- 尽量使用当前屏幕渲染，鉴于离屏渲染、CPU渲染可能带来的性能问题，一般情况下，我们要尽量使用当前屏幕渲染。
- 由于GPU的浮点运算能力比CPU强，CPU渲染的效率可能不如离屏渲染；但如果仅仅是实现一个简单的效果，直接使用CPU渲染的效率又可能比离屏渲染好，毕竟离屏渲染要涉及到缓冲区创建和上下文切换等耗时操作

### 12.如何高性能的画一个圆角？

```
label.layer.cornerRadius = 5
label.layer.masksToBounds = true
```
- 首先上面的方式是不可取的，会触发离屏渲染。
- 如果能够只用 cornerRadius解决问题，就不用优化。
- 如果必须设置masksToBounds，可以参考圆角视图的数量，如果数量较少（一页只有几个）也可以考虑不用优化。
- UIImageView的圆角通过直接截取图片实现，其它视图的圆角可以通过 Core Graphics 画出圆角矩形实现。

### 13.如何优化 APP 的内存？
- 同16题

### 14.如何优化 APP 的电量？
- 程序的耗电主要在以下四个方面：
    * CPU 处理
    * 定位
    * 网络
    * 图像
- 优化的途径主要体现在以下几个方面：
    * 尽可能降低 CPU、GPU 的功耗。
    * 尽量少用 定时器。
    * 优化 I/O 操作。
        * 不要频繁写入小数据，而是积攒到一定数量再写入
        * 读写大量的数据可以使用 Dispatch_io ，GCD 内部已经做了优化。
        * 数据量比较大时，建议使用数据库
    * 网络方面的优化
        * 减少压缩网络数据 （XML -> JSON -> ProtoBuf），如果可能建议使用 ProtoBuf。
        * 如果请求的返回数据相同，可以使用 NSCache 进行缓存
        * 使用断点续传，避免因网络失败后要重新下载。
        * 网络不可用的时候，不尝试进行网络请求
        * 长时间的网络请求，要提供可以取消的操作
        * 采取批量传输。下载视频流的时候，尽量一大块的进行下载，广告可以一次下载多个
    * 定位层面的优化
        * 如果只是需要快速确定用户位置，最好用 CLLocationManager 的 requestLocation 方法。定位完成后，会自动让定位硬件断电
        * 如果不是导航应用，尽量不要实时更新位置，定位完毕就关掉定位服务
        * 尽量降低定位精度，比如尽量不要使用精度最高的 kCLLocationAccuracyBest
        * 需要后台定位时，尽量设置 pausesLocationUpdatesAutomatically 为 YES，如果用户不太可能移动的时候系统会自动暂停位置更新
        * 尽量不要使用 startMonitoringSignificantLocationChanges，优先考虑 startMonitoringForRegion:
    * 硬件检测优化
        * 用户移动、摇晃、倾斜设备时，会产生动作(motion)事件，这些事件由加速度计、陀螺仪、磁力计等硬件检测。在不需要检测的场合，应该及时关闭这些硬件

### 15.假如Controller太臃肿，如何优化？
- 将网络请求抽象到单独的类中
    * 方便在基类中处理公共逻辑；
    * 方便在基类中处理缓存逻辑，以及其它一些公共逻辑；
    * 方便做对象的持久化。
- 将界面的封装抽象到专门的类中
    * 构造专门的 UIView 的子类，来负责这些控件的拼装。这是最彻底和优雅的方式，不过稍微麻烦一些的是，你需要把这些控件的事件回调先接管，再都一一暴露回 Controller。
- 构造 ViewModel
    * 借鉴MVVM。具体做法就是将 ViewController 给 View 传递数据这个过程，抽象成构造 ViewModel 的过程。
- 专门构造存储类
    * 专门来处理本地数据的存取。
- 整合常量

### 16.App 启动时都干了些什么事儿？
- 一般情况下，App 的启动分为冷启动和热启动。
    * 冷启动是指， App 点击启动前，它的进程不在系统里，需要系统新创建一个进程分配给它启动的情况。这是一次完整的启动过程。
    * 热启动是指 ，App 在冷启动后用户将 App 退后台，在 App 的进程还在系统里的情况下，用户重新启动进入 App 的过程，这个过程做的事情非常少。
- 一般而言，App 的启动时间，指的是从用户点击 App 开始，到用户看到第一个界面之间的时间。总结来说，App 的启动主要包括三个阶段：
    * main() 函数执行前；
    * main() 函数执行后；
    * 首屏渲染完成后。

#### main() 函数执行前
- 在 main() 函数执行前，系统主要会做下面几件事情：
    * 加载可执行文件（App 的.o 文件的集合）；
    * 加载动态链接库，进行 rebase 指针调整和 bind 符号绑定；
    * Objc 运行时的初始处理，包括 Objc 相关类的注册、category 注册、selector 唯一性检查等；
    * 初始化，包括了执行 +load() 方法、attribute((constructor)) 修饰的函数的调用、创建 C++ 静态全局变量。
- 相应地，这个阶段对于启动速度优化来说，可以做的事情包括：
    * 减少动态库加载。每个库本身都有依赖关系，苹果公司建议使用更少的动态库，并且建议在使用动态库的数量较多时，尽量将多个动态库进行合并。数量上，苹果公司建议最多使用 6 个非系统动态库。
    * 减少加载启动后不会去使用的类或者方法。
    * +load() 方法里的内容可以放到首屏渲染完成后再执行，或使用 +initialize() 方法替换掉。因为，在一个 +load() 方法里，进行运行时方法替换操作会带来 4 毫秒的消耗。不要小看这 4 毫秒，积少成多，执行 +load() 方法对启动速度的影响会越来越大。
    * 控制 C++ 全局变量的数量。

#### main() 函数执行后
- main() 函数执行后的阶段，指的是从 main() 函数执行开始，到 appDelegate 的 didFinishLaunchingWithOptions 方法里首屏渲染相关方法执行完成。
- 首页的业务代码都是要在这个阶段，也就是首屏渲染前执行的，主要包括了：
    * 首屏初始化所需配置文件的读写操作；
    * 首屏列表大数据的读取；
    * 首屏渲染的大量计算等。
- 很多时候，开发者会把各种初始化工作都放到这个阶段执行，导致渲染完成滞后。更加优化的开发方式，应该是从功能上梳理出哪些是首屏渲染必要的初始化功能，哪些是 App 启动必要的初始化功能，而哪些是只需要在对应功能开始使用时才需要初始化的。梳理完之后，将这些初始化功能分别放到合适的阶段进行。

#### 首屏渲染完成后
- 首屏渲染后的这个阶段，主要完成的是，非首屏其他业务服务模块的初始化、监听的注册、配置文件的读取等。从函数上来看，这个阶段指的就是截止到 didFinishLaunchingWithOptions 方法作用域内执行首屏渲染之后的所有方法执行完成。简单说的话，这个阶段就是从渲染完成时开始，到 didFinishLaunchingWithOptions 方法作用域结束时结束。

#### 优化
##### 功能级别的启动优化
- 功能级别的启动优化，就是要从 main() 函数执行后这个阶段下手。
- 优化的思路是： main() 函数开始执行后到首屏渲染完成前只处理首屏相关的业务，其他非首屏业务的初始化、监听注册、配置文件读取等都放到首屏渲染完成后去做。

##### 方法级别的启动优化
- 经过功能级别的启动优化，也就是将非首屏业务所需的功能滞后以后，从用户点击 App 到看到首屏的时间将会有很大程度的缩短，也就达到了优化 App 启动速度的目的。
- 在这之后，我们需要进一步做的，是检查首屏渲染完成前主线程上有哪些耗时方法，将没必要的耗时方法滞后或者异步执行。通常情况下，耗时较长的方法主要发生在计算大量数据的情况下，具体的表现就是加载、编辑、存储图片和文件等资源。

### 17.对 App 启动速度的监控
- 目前来看，对 App 启动速度的监控，主要有两种手段。
- 第一种方法是，定时抓取主线程上的方法调用堆栈，计算一段时间里各个方法的耗时。Xcode 工具套件里自带的 Time Profiler ，采用的就是这种方式。
- 这种方式的优点是，开发类似工具成本不高，能够快速开发后集成到你的 App 中，以便在真实环境中进行检查。
- 问题：
    * 定时间隔设置得长了，会漏掉一些方法，从而导致检查出来的耗时不精确；
    * 而定时间隔设置得短了，抓取堆栈这个方法本身调用过多也会影响整体耗时，导致结果不准确。
- 这个定时间隔如果小于所有方法执行的时间（比如 0.002 秒），那么基本就能监控到所有方法。但这样做的话，整体的耗时时间就不够准确。一般将这个定时间隔设置为 0.01 秒。这样设置，对整体耗时的影响小，不过很多方法耗时就不精确了。但因为整体耗时的数据更加重要些，单个方法耗时精度不高也是可以接受的，所以这个设置也是没问题的。
- 第二种方法是，对 objc_msgSend 方法进行 hook 来掌握所有方法的执行耗时。
- hook 方法的意思是，在原方法开始执行时换成执行其他你指定的方法，或者在原有方法执行前后执行你指定的方法，来达到掌握和改变指定方法的目的。
- hook objc_msgSend 这种方式的优点是非常精确，而缺点是只能针对 Objective-C 的方法。当然，对于 c 方法和 block 也不是没有办法，你可以使用 libffi 的 ffi_call 来达成 hook，但缺点就是编写维护相关工具门槛高。

### 18.如何做一个方法级别启动耗时检查工具来辅助分析和监控？
- 使用 hook objc_msgSend 方式来检查启动方法的执行耗时时，我们需要实现一个称手的启动时间检查工具。
- Objective-C 里每个对象都会指向一个类，每个类都会有一个方法列表，方法列表里的每个方法都是由 selector、函数指针和 metadata 组成的。
- objc_msgSend 本身是用汇编语言写的，这样做的原因主要有两个：
    * 一个原因是，objc_msgSend 的调用频次最高，在它上面进行的性能优化能够提升整个 App 生命周期的性能。而汇编语言在性能优化上属于原子级优化，能够把优化做到极致。所以，这种投入产出比无疑是最大的。
    * 另一个原因是，其他语言难以实现未知参数跳转到任意函数指针的功能。
- objc_msgSend 方法执行的逻辑是：先获取对象对应类的信息，再获取方法的缓存，根据方法的 selector 查找函数指针，经过异常错误处理后，最后跳到对应函数的实现。
- Facebook 开源了一个库，可以在 iOS 上运行的 Mach-O 二进制文件中动态地重新绑定符号，这个库叫 fishhook。
- fishhook 实现的大致思路是，通过重新绑定符号，可以实现对 c 方法的 hook。dyld 是通过更新 Mach-O 二进制的 __DATA segment 特定的部分中的指针来绑定 lazy 和 non-lazy 符号，通过确认传递给 rebind_symbol 里每个符号名称更新的位置，就可以找出对应替换来重新绑定这些符号。

### 19.如何对 App 包大小做优化
#### 官方 App Thinning
- App Thinning 是由苹果公司推出的一项可以改善 App 下载进程的新技术，主要是为了解决用户下载 App 耗费过高流量的问题，同时还可以节省用户 iOS 设备的存储空间。
- App Thinning 会专门针对不同的设备来选择只适用于当前设备的内容以供下载。
- 使用 App Thinning 后，用户下载时就只会下载一个适合自己设备的芯片指令集架构文件。
- App Thinning 有三种方式，包括：App Slicing、Bitcode、On-Demand Resources。
    * App Slicing，会在你向 iTunes Connect 上传 App 后，对 App 做切割，创建不同的变体，这样就可以适用到不同的设备。
    * On-Demand Resources，主要是为游戏多关卡场景服务的。它会根据用户的关卡进度下载随后几个关卡的资源，并且已经过关的资源也会被删掉，这样就可以减少初装 App 的包大小。
    * Bitcode ，是针对特定设备进行包大小优化，优化不明显。
- 其实，这里的大部分工作都是由 Xcode 和 App Store 来帮你完成的，你只需要通过 Xcode 添加 xcassets 目录，然后将图片添加进来即可。

#### 无用图片资源
- 图片资源的优化空间，主要体现在删除无用图片和图片资源压缩这两方面。而删除无用图片，又是其中最容易、最应该先做的。
- 删除无用图片的过程，可以概括为下面这 6 大步。
    * 通过 find 命令获取 App 安装包中的所有资源文件，比如 find /Users/daiming/Project/ -name。
    * 设置用到的资源的类型，比如 jpg、gif、png、webp。
    * 使用正则匹配在源码中找出使用到的资源名，比如 pattern = @"@"(.+?)""。
    * 使用 find 命令找到的所有资源文件，再去掉代码中使用到的资源文件，剩下的就是无用资源了。
    * 对于按照规则设置的资源名，我们需要在匹配使用资源的正则表达式里添加相应的规则，比如 @“image_%d”。
    * 确认无用资源后，就可以对这些无用资源执行删除操作了。这个删除操作，你可以使用 NSFileManger 系统类提供的功能来完成。
- 如果你不想自己重新写一个工具的话，可以选择开源的工具直接使用。我觉得目前最好用的是 LSUnusedResources，特别是对于使用编号规则的图片来说，可以通过直接添加规则来处理。

#### 图片资源压缩
- 对于 App 来说，图片资源总会在安装包里占个大头儿。对它们最好的处理，就是在不损失图片质量的前提下尽可能地作压缩。目前比较好的压缩方案是，将图片转成 WebP。
- 首先，我们一起看看选择 WebP 的理由：
    * WebP 压缩率高，而且肉眼看不出差异，同时支持有损和无损两种压缩模式。比如，将 Gif 图转为 Animated WebP ，有损压缩模式下可减少 64% 大小，无损压缩模式下可减少 19% 大小。
    * WebP 支持 Alpha 透明和 24-bit 颜色数，不会像 PNG8 那样因为色彩不够而出现毛边。

#### 代码瘦身
- 可执行文件就是 Mach-O 文件，其大小是由代码量决定的。通常情况下，对可执行文件进行瘦身，就是找到并删除无用代码的过程。而查找无用代码时，我们可以按照找无用图片的思路，即：
    * 首先，找出方法和类的全集；
    * 然后，找到使用过的方法和类；
    * 接下来，取二者的差集得到无用代码；
    * 最后，由人工确认无用代码可删除后，进行删除即可。

#### LinkMap 结合 Mach-O 找无用代码
- 我们可以通过分析 LinkMap 来获得所有的代码类和方法的信息。获取 LinkMap 可以通过将 Build Setting 里的 Write Link Map File 设置为 Yes，然后指定 Path to Link Map File 的路径就可以得到每次编译后的 LinkMap 文件了。
- LinkMap 文件分为三部分：Object File、Section 和 Symbols。其中：
    * Object File 包含了代码工程的所有文件；
    * Section 描述了代码段在生成的 Mach-O 里的偏移位置和大小；
    * Symbols 会列出每个方法、类、block，以及它们的大小。
- 通过 LinkMap ，你不光可以统计出所有的方法和类，还能够清晰地看到代码所占包大小的具体分布，进而有针对性地进行代码优化。
- 我们可以使用 MachOView 这个软件来查看 Mach-O 文件里的信息。

#### 通过 AppCode 找出无用代码
- 如果工程量不是很大的话，我还是建议你直接使用 AppCode 来做分析
- 用 AppCode 做分析的方法很简单，直接在 AppCode 里选择 Code->Inspect Code 就可以进行静态分析。
- 静态分析完以后，我们可以在 Unused code 里看到所有的无用代码,接下来，说一下这些无用代码的主要类型。
    * 无用类：Unused class 是无用类，Unused import statement 是无用类引入声明，Unused property 是无用的属性；
    * 无用方法：Unused method 是无用的方法，Unused parameter 是无用参数，Unused instance variable 是无用的实例变量，Unused local variable 是无用的局部变量，Unused value 是无用的值；
    * 无用宏：Unused macro 是无用的宏。
    * 无用全局：Unused global declaration 是无用全局声明。
- 看似 AppCode 已经把所有工作都完成了，其实不然。下面，我再和你列举下 AppCode 静态检查的问题：
    * JSONModel 里定义了未使用的协议会被判定为无用协议；
    * 如果子类使用了父类的方法，父类的这个方法不会被认为使用了；
    * 通过点的方式使用属性，该属性会被认为没有使用；
    * 使用 performSelector 方式调用的方法也检查不出来，比如 self performSelector:@selector(arrivalRefreshTime)；
    * 运行时声明类的情况检查不出来。比如通过 NSClassFromString 方式调用的类会被查出为没有使用的类，比如 layerClass = NSClassFromString(@“SMFloatLayer”)。还有以[[self class] accessToken] 这样不指定类名的方式使用的类，会被认为该类没有被使用。像 UITableView 的自定义的 Cell 使用 registerClass，这样的情况也会认为这个 Cell 没有被使用。
- 基于以上种种原因，使用 AppCode 检查出来的无用代码，还需要人工二次确认才能够安全删除掉。

#### 运行时检查类是否真正被使用过
- 即使你使用 LinkMap 结合 Mach-O 或者 AppCode 的方式，通过静态检查已经找到并删除了无用的代码,实际上，在 App 的不断迭代过程中，新人不断接手、业务功能需求不断替换，会留下很多无用代码。这些代码在执行静态检查时会被用到，但是线上可能连这些老功能的入口都没有了，更是没有机会被用户用到。也就是说，这些无用功能相关的代码也是可以删除的。

### 20.App 如何加载？
#### iOS 系统架构
- iOS 系统是基于 ARM 架构的，大致可以分为四层：
    * 最上层是用户体验层，主要是提供用户界面。这一层包含了 SpringBoard、Spotlight、Accessibility。
    * 第二层是应用框架层，是开发者会用到的。这一层包含了开发框架 Cocoa Touch。
    * 第三层是核心框架层，是系统核心功能的框架层。这一层包含了各种图形和媒体核心框架、Metal 等。
    * 第四层是 Darwin 层，是操作系统的核心，属于操作系统的内核态。这一层包含了系统内核 XNU、驱动等。
- 其中，用户体验层、应用框架层和核心框架层，属于用户态，是上层 App 的活动空间。Darwin 是用户态的下层支撑，是 iOS 系统的核心。
- Darwin 的内核是 XNU，而 XNU 是在 UNIX 的基础上做了很多改进以及创新。了解 XNU 的内部是怎么样的，将有助于我们解决系统层面的问题。

#### XNU
- XNU 内部由 Mach、BSD、驱动 API IOKit 组成，这些都依赖于 libkern、libsa、Platform Expert。如下图所示：

![image](https://static001.geekbang.org/resource/image/0f/7b/0f51e4995ead8b5b4c0e8cd2a987917b.png)

- 其中，Mach是作为 UNIX 内核的替代，主要解决 UNIX 一切皆文件导致抽象机制不足的问题，为现代操作系统做了进一步的抽象工作。 Mach 负责操作系统最基本的工作，包括进程和线程抽象、处理器调度、进程间通信、消息机制、虚拟内存管理、内存保护等。
- 进程对应到 Mach 是 Mach Task，Mach Task 可以看做是线程执行环境的抽象，包含虚拟地址空间、IPC 空间、处理器资源、调度控制、线程容器。
- 进程在 BSD 里是由 BSD Process 处理，BSD Process 扩展了 Mach Task，增加了进程 ID、信号信息等，BSD Process 里面包含了扩展 Mach Thread 结构的 Uthread。
- Mach 的模块包括进程和线程都是对象，对象之间不能直接调用，只能通过 Mach Msg 进行通信，也就是 mach_msg() 函数。在用户态的那三层中，也就是在用户体验层、应用框架层和核心框架层中，你可以通过 mach_msg_trap() 函数触发陷阱，从而切至 Mach，由 Mach 里的 mach_msg() 函数完成实际通信。
- 每个 Mach Thread 表示一个线程，是 Mach 里的最小执行单位。Mach Thread 有自己的状态，包括机器状态、线程栈、调度优先级（有 128 个，数字越大表示优先级越高）、调度策略、内核 Port、异常 Port。

#### XNU 怎么加载 App？
- iOS 的可执行文件和动态库都是 Mach-O 格式，所以加载 APP 实际上就是加载 Mach-O 文件。
- 其中，文件类型 filetype 表示了当前 Mach-O 属于哪种类型。Mach-O 包括以下几种类型。
    * OBJECT，指的是 .o 文件或者 .a 文件；
    * EXECUTE，指的是 IPA 拆包后的文件；
    * DYLIB，指的是 .dylib 或 .framework 文件；
    * DYLINKER，指的是动态链接器；
    * DSYM，指的是保存有符号信息用于分析闪退信息的文件。
- 加载 Mach-O 文件，内核会 fork 进程，并对进程进行一些基本设置，比如为进程分配虚拟内存、为进程创建主线程、代码签名等。用户态 dyld 会对 Mach-O 文件做库加载和符号解析。
- 可以看出，由于 Mach-O 文件很大， __mac_execve 函数会先为 Mach-O 分配一大块内存 imgp，接下来会初始化 imgp 里的公共数据。内存处理完，__mac_execve 函数就会通过 fork_create_child() 函数 fork 出一个新的进程。新进程 fork 后，会通过 exec_activate_image() 函数解析加载 Mach-O 文件到内存 imgp 里。最后，使用 task_set_main_thread_qos() 函数设置新 fork 出进程的主线程。
- 可以看出，加载 Mach-O 文件的是 exec_mach_imgact() 函数。exec_mach_imgact() 会通过 load_machfile() 函数加载 Mach-O 文件，根据解析 Mach-O 后得到的 load command 信息，通过映射方式加载到内存中。还会使用 activate_exec_state() 函数处理解析加载 Mach-O 后的结构信息，设置执行 App 的入口点。
- 设置完入口点后会通过 load_dylinker() 函数来解析加载 dyld，然后将入口点地址改成 dyld 的入口地址。这一步完后，内核部分就完成了 Mach-O 文件的加载。剩下的就是用户态层 dyld 加载 App 了。
- 总体来说，XNU 加载就是为 Mach-O 创建一个新进程，建立虚拟内存空间，解析 Mach-O 文件，最后映射到内存空间。流程可以概括为：
    * fork 新进程；
    * 为 Mach-O 分配内存；
    * 解析 Mach-O；
    * 读取 Mach-O 头信息；
    * 遍历 load command 信息，将 Mach-O 映射到内存；
    * 启动 dyld。

### 21.App 启动速度怎么做优化与监控？
- 一般情况下，App 的启动分为冷启动和热启动。
    * 冷启动是指， App 点击启动前，它的进程不在系统里，需要系统新创建一个进程分配给它启动的情况。这是一次完整的启动过程。
    * 热启动是指 ，App 在冷启动后用户将 App 退后台，在 App 的进程还在系统里的情况下，用户重新启动进入 App 的过程，这个过程做的事情非常少。
- 一般而言，App 的启动时间，指的是从用户点击 App 开始，到用户看到第一个界面之间的时间。总结来说，App 的启动主要包括三个阶段：
    * main() 函数执行前；
    * main() 函数执行后；
    * 首屏渲染完成后。

#### main() 函数执行前
- 在 main() 函数执行前，系统主要会做下面几件事情：
    * 加载可执行文件（App 的.o 文件的集合）；
    * 加载动态链接库，进行 rebase 指针调整和 bind 符号绑定；
    * Objc 运行时的初始处理，包括 Objc 相关类的注册、category 注册、selector 唯一性检查等；
    * 初始化，包括了执行 +load() 方法、attribute((constructor)) 修饰的函数的调用、创建 C++ 静态全局变量。
- 相应地，这个阶段对于启动速度优化来说，可以做的事情包括：
    * 减少动态库加载。每个库本身都有依赖关系，苹果公司建议使用更少的动态库，并且建议在使用动态库的数量较多时，尽量将多个动态库进行合并。数量上，苹果公司建议最多使用 6 个非系统动态库。
    * 减少加载启动后不会去使用的类或者方法。
    * +load() 方法里的内容可以放到首屏渲染完成后再执行，或使用 +initialize() 方法替换掉。因为，在一个 +load() 方法里，进行运行时方法替换操作会带来 4 毫秒的消耗。不要小看这 4 毫秒，积少成多，执行 +load() 方法对启动速度的影响会越来越大。
    * 控制 C++ 全局变量的数量。

#### main() 函数执行后
- main() 函数执行后的阶段，指的是从 main() 函数执行开始，到 appDelegate 的 didFinishLaunchingWithOptions 方法里首屏渲染相关方法执行完成。
- 首页的业务代码都是要在这个阶段，也就是首屏渲染前执行的，主要包括了：
    * 首屏初始化所需配置文件的读写操作；
    * 首屏列表大数据的读取；
    * 首屏渲染的大量计算等。
- 很多时候，开发者会把各种初始化工作都放到这个阶段执行，导致渲染完成滞后。更加优化的开发方式，应该是从功能上梳理出哪些是首屏渲染必要的初始化功能，哪些是 App 启动必要的初始化功能，而哪些是只需要在对应功能开始使用时才需要初始化的。梳理完之后，将这些初始化功能分别放到合适的阶段进行。

#### 首屏渲染完成后
- 首屏渲染后的这个阶段，主要完成的是，非首屏其他业务服务模块的初始化、监听的注册、配置文件的读取等。从函数上来看，这个阶段指的就是截止到 didFinishLaunchingWithOptions 方法作用域内执行首屏渲染之后的所有方法执行完成。简单说的话，这个阶段就是从渲染完成时开始，到 didFinishLaunchingWithOptions 方法作用域结束时结束。

#### 优化
##### 功能级别的启动优化
- 功能级别的启动优化，就是要从 main() 函数执行后这个阶段下手。
- 优化的思路是： main() 函数开始执行后到首屏渲染完成前只处理首屏相关的业务，其他非首屏业务的初始化、监听注册、配置文件读取等都放到首屏渲染完成后去做。

##### 方法级别的启动优化
- 经过功能级别的启动优化，也就是将非首屏业务所需的功能滞后以后，从用户点击 App 到看到首屏的时间将会有很大程度的缩短，也就达到了优化 App 启动速度的目的。
- 在这之后，我们需要进一步做的，是检查首屏渲染完成前主线程上有哪些耗时方法，将没必要的耗时方法滞后或者异步执行。通常情况下，耗时较长的方法主要发生在计算大量数据的情况下，具体的表现就是加载、编辑、存储图片和文件等资源。

## 调试技巧 & 软件使用
### 1.`LLDB` 调试。
### 2.断点调试- breakPoint。
### 3.`NSAssert` 的使用。
### 4.`Charles` 的使用。
    - 使用 Charles 下载过去任意版本的 App。
### 5.`Reveal` 的使用。
### 6.iOS 常见的崩溃类型有哪些？
- 崩溃的类型：
    * 数组越界：在取数据索引时越界，App 会发生崩溃。还有一种情况，就是给数组添加了 nil 会崩溃。
    * 多线程问题：在子线程中进行 UI 更新可能会发生崩溃。多个线程进行数据的读取操作，因为处理时机不一致，比如有一个线程在置空数据的同时另一个线程在读取这个数据，可能会出现崩溃情况。
    * 主线程无响应：如果主线程超过系统规定的时间无响应，就会被 Watchdog 杀掉。这时，崩溃问题对应的异常编码是 0x8badf00d。关于这个异常编码，我还会在后文和你说明。
    * 野指针：指针指向一个已删除的对象访问内存区域时，会出现野指针崩溃。野指针问题是需要我们重点关注的，因为它是导致 App 崩溃的最常见，也是最难定位的一种情况。关于野指针等内存相关问题，我会在第 14 篇文章“临近 OOM，如何获取详细内存分配信息，分析内存问题？”里和你详细说明。
- 你可以看一下下面这幅图，我列出了常见的部分崩溃情况：

![image](https://static001.geekbang.org/resource/image/f9/fe/f97dda3b49351f74747dd74128a0ddfe.png)

- 通过这张图片，我们可以看到， KVO 问题、NSNotification 线程问题、数组越界、野指针等崩溃信息，是可以通过信号捕获的。但是，像后台任务超时、内存被打爆、主线程卡顿超阈值等信息，是无法通过信号捕捉到的。

#### 如何捕获
##### 信号可捕获的崩溃日志收集
- 收集崩溃日志最简单的方法，就是打开 Xcode 的菜单选择 Product -> Archive。
- 然后，在提交时选上“Upload your app’s symbols to receive symbolicated reports from Apple”，以后你就可以直接在 Xcode 的 Archive 里看到符号化后的崩溃日志了。

##### 信号捕获不到的崩溃信息怎么收集？
- 是不是经常会遇到这么一种情况，App 退到后台后，即使代码逻辑没有问题也很容易出现崩溃。而且，这些崩溃往往是因为系统强制杀掉了某些进程导致的，而系统强杀抛出的信号还由于系统限制无法被捕获到。
- iOS 后台保活的 5 种方式：Background Mode、Background Fetch、Silent Push、PushKit、Background Task。
    * 使用 Background Mode 方式的话，App Store 在审核时会提高对 App 的要求。通常情况下，只有那些地图、音乐播放、VoIP 类的 App 才能通过审核。
    * Background Fetch 方式的唤醒时间不稳定，而且用户可以在系统里设置关闭这种方式，导致它的使用场景很少。
    * Silent Push 是推送的一种，会在后台唤起 App 30 秒。它的优先级很低，会调用 application:didReceiveRemoteNotifiacation:fetchCompletionHandler: 这个 delegate，和普通的 remote push notification 推送调用的 delegate 是一样的。
    * PushKit 后台唤醒 App 后能够保活 30 秒。它主要用于提升 VoIP 应用的体验。
    * Background Task 方式，是使用最多的。App 退后台后，默认都会使用这种方式。
- 在你的程序退到后台以后，只有几秒钟的时间可以执行代码，接下来就会被系统挂起。进程挂起后所有线程都会暂停，不管这个线程是文件读写还是内存读写都会被暂停。但是，数据读写过程无法暂停只能被中断，中断时数据读写异常而且容易损坏文件，所以系统会选择主动杀掉 App 进程。
- 而 Background Task 这种方式，就是系统提供了 beginBackgroundTaskWithExpirationHandler 方法来延长后台执行时间，可以解决你退后台后还需要一些时间去处理一些任务的诉求。

##### 如何避免后台崩溃呢？
- App 退后台后，如果执行时间过长就会导致被系统杀掉。那么，如果我们要想避免这种崩溃发生的话，就需要严格控制后台数据的读写操作。比如，你可以先判断需要处理的数据的大小，如果数据过大，也就是在后台限制时间内或延长后台执行时间后也处理不完的话，可以考虑在程序下次启动或后台唤醒时再进行处理。
- 同时，App 退后台后，这种由于在规定时间内没有处理完而被系统强制杀掉的崩溃，是无法通过信号被捕获到的。这也说明了，随着团队规模扩大，要想保证 App 高可用的话，后台崩溃的监控就尤为重要了。

##### 怎么去收集退后台后超过保活阈值而导致信号捕获不到的那些崩溃信息呢？
- 采用 Background Task 方式时，我们可以根据 beginBackgroundTaskWithExpirationHandler 会让后台保活 3 分钟这个阈值，先设置一个计时器，在接近 3 分钟时判断后台程序是否还在执行。如果还在执行的话，我们就可以判断该程序即将后台崩溃，进行上报、记录，以达到监控的效果。

##### 还有哪些信号捕获不到的崩溃情况？怎样监控其他无法通过信号捕获的崩溃信息？
- 其他捕获不到的崩溃情况还有很多，主要就是内存打爆和主线程卡顿时间超过阈值被 watchdog 杀掉这两种情况。
- 其实，监控这两类崩溃的思路和监控后台崩溃类似，我们都先要找到它们的阈值，然后在临近阈值时还在执行的后台程序，判断为将要崩溃，收集信息并上报。
- 对于内存打爆信息的收集，你可以采用内存映射（mmap）的方式来保存现场。主线程卡顿时间超过阈值这种情况，你只要收集当前线程的堆栈信息就可以了。

##### 采集到崩溃信息后如何分析并解决崩溃问题呢？
- 通过上面的内容，我们已经解决了崩溃信息采集的问题。现在，我们需要对这些信息进行分析，进而解决 App 的崩溃问题。
- 我们采集到的崩溃日志，主要包含的信息为：进程信息、基本信息、异常信息、线程回溯。
    * 进程信息：崩溃进程的相关信息，比如崩溃报告唯一标识符、唯一键值、设备标识；
    * 基本信息：崩溃发生的日期、iOS 版本；
    * 异常信息：异常类型、异常编码、异常的线程；
    * 线程回溯：崩溃时的方法调用栈。
- 通常情况下，我们分析崩溃日志时最先看的是异常信息，分析出问题的是哪个线程，在线程回溯里找到那个线程；然后，分析方法调用栈，符号化后的方法调用栈可以完整地看到方法调用的过程，从而知道问题发生在哪个方法的调用上。
- 方法调用栈顶，就是最后导致崩溃的方法调用。完整的崩溃日志里，除了线程方法调用栈还有异常编码。异常编码，就在异常信息里。
- 一些被系统杀掉的情况，我们可以通过异常编码来分析。你可以在维基百科上，但常见的就是如下三种：
    * 0x8badf00d，表示 App 在一定时间内无响应而被 watchdog 杀掉的情况。
    * 0xdeadfa11，表示 App 被用户强制退出。
    * 0xc00010ff，表示 App 因为运行造成设备温度太高而被杀掉。
- 0x8badf00d 这种情况是出现最多的。当出现被 watchdog 杀掉的情况时，我们就可以把范围控制在主线程被卡的情况。我会在第 13 篇文章“如何利用 RunLoop 原理去监控卡顿？”中，和你详细说明如何去监控这种情况来防范和快速定位到问题。
- 0xdeadfa11 的情况，是用户的主动行为，我们不用太关注。
- 0xc00010ff 这种情况，就要对每个线程 CPU 进行针对性的检查和优化。我会在第 18 篇文章“怎么减少 App 的电量消耗？”中，和你详细说明。

### 7.当页面 AutoLayout 出现了问题，怎样快速调试？

## 扩展问题
### 1.无痕埋点
### 2.APM（应用程序性能监测）
### 3.Hot Patch（热修补）
### 4.崩溃的处理
### 补充：各个app之间是怎么相互切换的


## 其他问题
### 1.面向对象的三个要素
- 封装
    * 封装，就是将客观事物抽象为逻辑实体，实体的属性和功能相结合，形成一个有机的整体。并对实体的属性和功能实现进行访问控制，向信任的实体开放，对不信任的实体隐藏。，通过开放的外部接口即可访问，无需知道功能如何实现。
    * 也就是说，封装主要有以下目的：
        * 可隐藏实体实现的细节
        * 提高安全性，设定访问控制，只允许具有特定权限的使用者调用。
        * 简化编程，调用方无需知道功能是怎么实现的，即可调用。
- 继承
    * 继承，在继承机制下形成有层级的类，使得低层级的类可以延用高层级类的特征和方法。继承的实现方式有两种：实现继承、接口继承。
    * 实现继承：直接使用基类公开的属性和方法，无需额外编码。
    * 接口继承：仅使用接口公开的属性和方法名称，需要子类实现。
    * 也就是说，继承有以下目的：
        * 复用代码，减少类的冗余代码，减少开发工作量。
        * 使得类与类之间产生关系，为多态的实现打下基础。
- 多态
    * 多态，是指一个类的同名方法，在不同情况下的实现细节不同。多态机制实现不同的内部实现结构共用同一个外部接口。
    * 也就是说，多态有以下目的：
        * 一个外部接口可被多个同类使用。
        * 不同对象调用同个方法，可有不同实现。

### 2.多态？
- 多态实现的三个必要条件是：继承、重写（子类继承父类后，对继承的方法重新定义）、父类应用指向子类对象。所以，多态的实现是基于继承的。

### 补充：事务的特征
- 事务的四个特征：
    * 原子性 Atomic：事务中的所有操作要么都执行，要么都不执行
    * 一致性 Consistency：事务执行的结果从一个状态到另一个状态时保持一致。即当事务提交成功时，保存一致性的结果；当事务提交不成功时，数据库将处在不一样的状态，这种状态应该撤销
    * 隔离性 Isolation：并发执行事务时，事务之间不能互相干扰
    * 持久性 Durability：事务一旦提交成功，数据修改是永久的
- 原子性保持了事务的一致性，隔离性保证多个事务间不互相干扰。否则，即便每个事务都能确保数据的原子性和一致性，多个事务并发执行时，也可能出现不一致的状态。

### 补充：事务状态
- 活动状态：事务执行前的状态
- 部分提交状态：事务的最后一条语句执行完毕，结果已经在内存缓冲区中，还没有写入磁盘
- 失败状态：事务没有正常执行，应该回滚
- 终止状态：事务回滚并且数据库恢复到事务执行前的状态
- 提交状态：数据的更改完全写入磁盘

### 3.Java，python，OC运行效率孰高？
- OC最高，OC大于java大于python
- oc方法调用的需要经历查缓存，查方法表，查父类方法表，如果都差不多就会进行动态方法决议，如果还是不行，就执行消息转发机制，如果还是无法处理就crash。但是大部分在方法缓存的时候就能找到，苹果有函数缓存机制，当缓存生效时性能与c差不多。
- Java是静态语言静态编译的，直接执行，速度上要比Python快的很多。而Python动态类型语言，一边执行一边编译，所以要比Java慢。

### 4.Property，其中copy如何？
- 用途：
    * NSString、NSArray、NSDictionary 等等经常使用copy关键字，是因为他们有对应的可变类型：NSMutableString、NSMutableArray、NSMutableDictionary；
    * lock 也经常使用 copy 关键字
- block 使用 copy 是从 MRC 遗留下来的“传统”,在 MRC 中,方法内部的 block 是在栈区的,使用 copy 可以把它放到堆区.在 ARC 中写不写都行：对于 block 使用 copy 还是 strong 效果是一样的，但写上 copy 也无伤大雅，还能时刻提醒我们：编译器自动对 block 进行了 copy 操作。如果不写 copy ，该类的调用者有可能会忘记或者根本不知道“编译器会自动对 block 进行了 copy 操作”，他们有可能会在调用之前自行拷贝属性值。这种操作多余而低效。
- 下面做下解释：
    * copy 此特质所表达的所属关系与 strong 类似。然而设置方法并不保留新值，而是将其“拷贝” (copy)。
    * 当属性类型为 NSString 时，经常用此特质来保护其封装性，因为传递给设置方法的新值有可能指向一个 NSMutableString 类的实例。这个类是 NSString 的子类，表示一种可修改其值的字符串，此时若是不拷贝字符串，那么设置完属性之后，字符串的值就可能会在对象不知情的情况下遭人更改。所以，这时就要拷贝一份“不可变” (immutable)的字符串，确保对象中的字符串值不会无意间变动。只要实现属性所用的对象是“可变的” (mutable)，就应该在设置新属性值时拷贝一份。
    * 用 @property 声明 NSString、NSArray、NSDictionary 经常使用 copy 关键字，是因为他们有对应的可变类型：NSMutableString、NSMutableArray、NSMutableDictionary，他们之间可能进行赋值操作，为确保对象中的字符串值不会无意间变动，应该在设置新属性值时拷贝一份。

### 5.Property(nonatomatic, copy) NSMutableArray有什么问题？
- 两个问题：
    * 添加,删除,修改数组内的元素的时候,程序会因为找不到对应的方法而崩溃.因为copy就是复制一个不可变 NSArray 的对象；
    * 使用了 atomic 属性会严重影响性能 ；
- 第一个问题：
    * 因为父类指针可以指向子类对象,使用 copy 的目的是为了让本对象的属性不受外界影响,使用 copy 无论给我传入是一个可变对象还是不可对象,我本身持有的就是一个不可变的副本.
- 第二个问题：
    * 该属性使用了同步锁，会在创建时生成一些额外的代码用于帮助编写多线程程序，这会带来性能问题，通过声明nonatomic可以节省这些虽然很小但是不必要额外开销。
    * 在默认情况下，由编译器所合成的方法会通过锁定机制确保其原子性(atomicity)。如果属性具备 nonatomic 特质，则不使用同步锁。请注意，尽管没有名为“atomic”的特质(如果某属性不具备 nonatomic 特质，那它就是“原子的”(atomic))。
    * 在iOS开发中，你会发现，几乎所有属性都声明为 nonatomic。
    * 一般情况下并不要求属性必须是“原子的”，因为这并不能保证“线程安全” ( thread safety)，若要实现“线程安全”的操作，还需采用更为深层的锁定机制才行。例如，一个线程在连续多次读取某属性值的过程中有别的线程在同时改写该值，那么即便将属性声明为atomic，也还是会读到不同的属性值。
    * 因此，开发iOS程序时一般都会使用 nonatomic 属性。但是在开发 Mac OS X 程序时，使用atomic 属性通常都不会有性能瓶颈。

### 6.Copy和MutableCopy的区别？
#### 对非集合类对象的 copy 与 mutableCopy 操作；
- 在非集合类对象中：对 immutable 对象进行 copy 操作，是指针复制，mutableCopy 操作时内容复制；对 mutable 对象进行 copy 和 mutableCopy 都是内容复制。用代码简单表示如下：
    * [immutableObject copy] // 浅复制
    * [immutableObject mutableCopy] //深复制
    * [mutableObject copy] //深复制
    * [mutableObject mutableCopy] //深复制
- 用 @property声明NSString、NSArray、NSDictionary 经常使用 copy关键字，是因为他们有对应的可变类型：NSMutableString、NSMutableArray、NSMutableDictionary，他们之间可能进行赋值操作，为确保对象中的字符串值不会无意间变动，应该在设置新属性值时拷贝一份。

#### 对集合类对象的 copy 与 mutableCopy 操作。
- 集合类对象是指 NSArray、NSDictionary、NSSet ... 之类的对象。
- 集合类对象中，对 immutable 对象进行 copy，是指针复制， mutableCopy 是内容复制；对 mutable 对象进行 copy 和 mutableCopy 都是内容复制。但是：集合对象的内容复制仅限于对象本身，对象元素仍然是指针复制。

### 7.解释下类别的原理
### 8.解释下封装，重载
### 9.OC存在多重继承吗？
### 10.了解表视图吗，解释一下复用原理
### 11.说明一下表视图的滑动卡顿的优化方法
### 12.viewDidLoad和viewDidAppear的调用时机（一次和多次的区别）；
### 13.页面间的传值方式有哪些（公有属性，公有方法和协议，block传值，通知，extern全局变量传值，NSUserDefault简单数据存储传值）；
### 14.在OC中对象方法的几种访问权限，分别是什么？
### 15.列出 #import 和 #include 的区别，另外什么时候使用@class？
### 16.`load` 和 `Initialize` 的区别?
### 17.`Designated Initializer`的规则？
### 18.`App` 编译过程有了解吗？
### 19.介绍下App启动的完成过程？
- 先加载Main函数
- 在Main函数里的 UIApplicationMain方法中，创建Application对象 创建Application的Delegate对象
- 创建主循环，代理对象开始监听事件
- 启动完毕会调用 didFinishLaunching方法，并在这个方法中创建UIWindow
- 设置UIWindow的根控制器是谁
- 如果有storyboard，会根据info.plist中找到应用程序的入口storyboard并加载箭头所指的控制器
- 显示窗口
- 其中在didFinishLaunching方法到窗口显示其中有AppDelegate,ViewController,MainView（控制器的View）,ChildView（子控件的View）的18个方法：
    * AppDelegate中的：
        * application:didFinishLaunchingWithOptions:
        * applicationDidBecomeActive:
    * ViewController中的：
        * loadView
        * viewDidLoad
        * load
        * initialize
        * viewWillAppear
        * viewWillLayoutSubviews
        * viewDidLayoutSubviews
        * viewDidAppear
    * MainView（控制器的View）中的
        * initWithCoder（如果没有storyboard就会调用initWithFrame，这里两种方法视为一种）
        * awakeFromNib
        * layoutSubviews
        * drawRect
    * ChildView（子控件View）中的：
        * initWithCoder（如果没有storyboard就会调用initWithFrame，这里两种方法视为一种）
        * awakeFromNib
        * layoutSubviews
        * drawRect
- 十八个方法排个顺序

```
+ (void)load; //这是应用程序启动就会调用的方法，在这个方法里写的代码最先调用

+ (void)initialize; //这个是需要用到本类时才调用，这个方法里一般写设置导航控制器的主题啊之类的，
//如果在后面的方法设置导航栏主题就晚了！（当然在上面的方法里也能写）

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions;
//这个方法里面会创建UIWindow，设置根控制器并展现，
//比如某些应用程序要加载授权页面也是在这加，也可以设置观察者，监听到通知切换根控制器

ChildView - (instancetype)initWithCoder:(NSCoder *)aDecoder;
//这里反正我是万万没想到，childView的initwithcoder会在MainView的方法之前调用，
//父的都还没出来，就先整子控件？ 有了解比较透彻的博友恳请告诉我谢谢。

MainView - (instancetype)initWithCoder:(NSCoder *)aDecoder;
// 就是关于应用程序的数据存储后的解档操作。

MainView - (void)awakeFromNib;
//在这个方法里设置view的背景等一系列普通操作，不要写关于frame的还不准，
//在使用IB的时候才会涉及到此方法的使用，当.nib文件被加载的时候，
//会发送一个awakeFromNib的消息到.nib文件中的每个对象，
//每个对象都可以定义自己的awakeFromNib函数来响应这个消息，执行一些必要的操作。

ChildView - (void)awakeFromNib
//子控件也有本方法，重写父类的方法。基本用法同上

- (void)loadView; 
//创建视图的层次结构，这里需要注意，
//在没有创建控制器的view的情况下不能直接写 self.view 因为self.view的底层是：
    if（_view == nil）{
　   　_view = [self loadView]
    }
//所以这么写会直接造成死循环。
//如果重写这个loadView方法里面什么都不写，会显示黑屏

- (void)viewDidLoad;
//卧槽，这个方法是用的最多的方法，但是在之后的开发中就会发现越来越不靠谱，
//很多东西都还没加载完毕，各种取值都不准确，很少在这里面写东西了。 
//这里只是把视图元件加载完成

- (void)viewWillAppear:(BOOL)animated;
//视图将要出现，这个方法用的非常多，比如如果要设置导航栏的setNavigationBarHiden:animate: 
//就必须要在这里写，才能完美契合，不卡跳。 还有很多比如监听屏幕旋转啦，
 
//viewWillTransitionToSize:可能要在本方法里再调一次，
//或者就是新到这个界面要reloadData或是自动下拉刷新等 都是写在本方法里

- (void)viewWillLayoutSubviews;
//视图将要布局子视图，苹果建议的设置界面布局属性的方法，
//这个方法和viewWillAppear里，系统的底层都是没有写任何代码的，也就是说这里面不写super 也是可以的

MainView  - (void)layoutSubviews;
//在这个方法里一般设置子控件的frame，因为这里相当于是布局基本完成了，
//设置时取到的frame或者是self.bounds才最准，如果在awakeFromeNib里写会不准确 。
//还有这里要切记千万不能把super layoutSubviews忘了，可能最后都很难找到这个bug

- (void)viewDidLayoutSubviews;
//这个方法我也是玩玩没想到，控制器的view的子控件还没有布局好呢，怎么这个控制器就已经说布局全部完成了？
//那后边的布局就不等了？ 有独到见解的也恳请你告诉我，这其中苹果的意思到底是什么。

ChildView - (void)layoutSubviews;
//控制器的子控件里的子控件的布局就在这里写了。

MainView - (void)drawRect:(CGRect)rect;
//因为默认所有额UI控件都是画上去的，在这一步就是把所有的东西画上去，
//有时候需要用到Quartz2D的知识的时候都是在这个方法里话，但也是要注意别忘了写super，
//不然系统原本的东西就都画不上来了，这里要建议尽可能使用贝塞尔路径画图形，
//因为系统默认的那个上下文画法有时可能会内存泄露。drawRect方法只能在加载时调用一次，
//如果后面还需要调用，比如下载进度的圆弧，需要一直刷帧，
//就要使用setNeedsDisplay来定时多次调用本方法

ChildView - (void)drawRect:(CGRect)rect;
//view的子控件内部的画图方法，有时可以自己自定义label 中间带个删除线的（用来写打折前的原价） 就是在这里画根线 。

- (void)viewDidAppear:(BOOL)animated;
//把上面的画图都画完了，这里就会显示，视图完全加载完成。
//在这里的操作可能就是设置页面的一些动画,或者是设置tableView，collectionView，
//QQ聊天页面啥的滚动到底部scrollToIndexPath之类的代码操作

- (void)applicationDidBecomeActive:(UIApplication *)application;
//最后这是AppDelegate的应用程序获取焦点方法，真正到了这里，才是所有东西全部加载完毕，应用程序整装待发保持最佳状态等待用户操作。
//这个方法中一般会写关于弹出键盘的方法，比如有的用户登录界面为了更好的用户体验，
//就让你在刚打开程序来到登录界面的时候，光标的焦点就自动在账号的文本框里闪烁，
//也就是设置账号文本框为第一响应者。键盘在页面加载完毕后从下方弹出，这种代码一般就在本方法写。

```

### 20.`JS` 和 `Native` 交互。
### 21.`LoadView`方法了解吗？
### 22.说一下对 `APNS` 的认识？
### 23：简述Xcode7和Xcode8的异同
### 24：描述iOS 10的一些新特性（包括系统和开发环境）
### 25.App 上有一数据列表，客户端和服务端均没有任何缓存，当服务端有数据更新时，该列表在 wifi 下能获取到数据，在 4G 下刷新不到，但是在 4g 环境下其他 App 都可以正常打开，分析其产生的原因？
### 26.是否了解链式编程？
### 27.dSYM你是如何分析的
- 我们在iOS开发过程中一定会跟符号表（dSYM文件）打交道，它是我们不可或缺的定位bug的小帮手。我们都知道，每次编译都会生成一个dSYM文件，当我们的应用程序出现奔溃时，dSYM文件能帮我们定位到应用程序的代码奔溃到哪里了。
- 符号表是内存地址与函数名、文件名、行号的映射表。符号表元素如下所示：

```
<起始地址> <结束地址> <函数> [<文件名:行号>]
```
- dSYM是如何分析的
    * 方法1 使用XCode，这种方法可能是最容易的方法了。
        * 要使用Xcode符号化 crash log，你需要下面所列的3个文件：crash报告（.crash文件），符号文件(.dsymb文件)，应用程序文件(appName.app文件，把IPA文件后缀改为zip，然后解压，Payload目录下的appName.app文件),这里的appName是你的应用程序的名称。把这3个文件放到同一个目录下，打开Xcode的Window菜单下的organizer，然后点击Devices tab，然后选中左边的Device Logs。然后把.crash文件拖到Device Logs或者选择下面的import导入.crash文件。这样你就可以看到crash的详细log了。
        * 方法2 使用命令行工具symbolicatecrash，有时候Xcode不能够很好的符号化crash文件。我们这里介绍如何通过symbolicatecrash来手动符号化crash log。在处理之前，请依然将“.app“, “.dSYM”和 ".crash"文件放到同一个目录下。现在打开终端(Terminal)然后输入如下的命令：export DEVELOPER_DIR=/Applications/Xcode.app/Contents/Developer，然后输入命令：/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/Library/PrivateFrameworks/DTDeviceKitBase.framework/Versions/A/Resources/symbolicatecrash appName.crash appName.app > appName.log；现在，符号化的crash log就保存在appName.log中了。
        * 方法3 使用命令行工具atos，如果你有多个“.ipa”文件，多个".dSYMB"文件，你并不太确定到底“dSYMB”文件对应哪个".ipa"文件，那么，这个方法就非常适合你。特别当你的应用发布到多个渠道的时候，你需要对不同渠道的crash文件，写一个自动化的分析脚本的时候，这个方法就极其有用。
