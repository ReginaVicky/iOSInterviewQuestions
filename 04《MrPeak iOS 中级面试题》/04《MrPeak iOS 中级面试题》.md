# iOSInterviewQuestion
## 知乎上MrPeak大神的面试题（附答案）

- 04《iOS中级面试题》，面试题来源是MrPeak大神在知乎上发的帖子[《如何面试iOS 工程师》](https://www.zhihu.com/question/19604641)
- 如有纰漏，请向微博[@爱吃兔兔的胡萝卜吖](https://weibo.com/6447187962/)反馈。


# 索引

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
13.谈下Objective C都有哪些锁机制，你一般用哪个？
14.聊下HTTP post的body体使用form-urlencoded和multipart/form-data的区别。
15.让你设计一种机制检测UIViewController的内存泄漏，你会怎么做？
16.通过[UIImage imageNamed:]生成的对象什么时候被释放？
17.applicationWillEnterForeground和applicationDidBecomeActive都会在哪些场景下被调用？举例越多越好。
18.如何终止正在运行的工作线程？
19.穷举iOS下所有的本地持久化方案。
20.如果公司强制996，你有什么心里话要对老板说吗？