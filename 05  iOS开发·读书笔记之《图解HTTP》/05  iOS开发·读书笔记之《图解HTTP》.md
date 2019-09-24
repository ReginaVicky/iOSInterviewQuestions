# 读书笔记之《图解HTTP》
## 第一章 了解Web与网络基础
### 1.1 使用HTTP协议访问Web
- 通过发送请求获取服务器资源的Web浏览器等，都可成为客户端；
- Web使用一种名为HTTP（HyperText Transfer Protocol，超文转移协议，超文本传输协议的译法并不严谨。）的协议作为规范，完成从客户端到服务器端等一系列运作流程。而协议是指规则的约定。可以说，Web是建立在HTTP协议上通信的。
![IMG_2445.JPG](https://upload-images.jianshu.io/upload_images/1197643-4dc248ba91caa3a3.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 1.3 网络基础TCP/IP
- 通常使用的网络（包括互联网）是在 TCP/IP 协议族的基础上运作的。而 HTTP 属于它的一个子集。
#### TCP/IP 协议族
- 协议：不同的硬件设备、操作系统之间需要通信的话需要遵循相同的规则，这种规则统称为 协议（protocol）。
- 计算机与网络设备之间要相互通信，双方就必须基于相同的方法。比如：如何探测到通信目标、由哪一边先发起通信、使用哪种语言进行通信、怎样结束通信等都需要遵循相同的协议。
- 协议中存在各式各样的内容，想这样把与互联网相关的协议集合起来总称为TCP/IP。
- 也有这么认为，TCP/IP是指TCP和IP这两种协议。
- 还有认为，TCP/IP是在IP协议的通信过程中，使用到的协议族的统称。
#### TCP/IP的分层管理
- TCP/IP 协议族里很重要的一点就是分层。TCP/IP 协议族分为4层，从上到下分别是：应用层、传输层、网络层和数据链路层。
- TCP/IP协议族各层的作用如下：
    - 应用层：应用层决定了向用户提供应用服务时通信的活动；TCP/IP协议族内预存了各类通用的应用服务。比如，FTP和DNS服务就是其中两类。HTTP协议也处于该层
    - 传输层：传输层对上层应用层，提供处于网络连接中的两台计算机之间的数据传输。在传输层有两个性质不同的协议：TCP和UDP。
    - 网络层：网络层用来处理在网络上流动的数据包。数据包是网络传输的最小数据单位。改层规定了通过怎样的路径到达对方计算机，并把数据包栓送给对方，与对方计算机之间通过多态计算机或网络设备进行传输时，网络层所起的作用就是在众多的选项内选择一条传输路线。
    - 链路层：用来处理连接网络的硬件部分。包括控制操作系统、硬件的设备驱动、NIC，及光纤等物理可见部分。硬件上的范畴君在链路层的作用范围之内。
#### TCP/IP 通信传输流
![IMG_2463.JPG](https://upload-images.jianshu.io/upload_images/1197643-ae3adaf0ec17d470.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 利用TCP/IP协议族进行网络通信时，会通过分层顺序与对方进行通信。发送端从应用层往下走，接收端则往应用层往上走。
![IMG_2464.JPG](https://upload-images.jianshu.io/upload_images/1197643-2e748c932707ed3c.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 我们用HTTP距离来说明，首先作为发送端的客户端在应用层发出一个想看某个WEb页面的HTTP请求，接着，为了传输方便，在传输层把从应用层处都收到的数据进行分割，并在各个报文上打上标记序号及端口号后转发给网络层。在网络层，增加作为通信目的地的MAC地址后转发给链路层。这样一来，发往网络的通信请求就准备去全了。
- 接收端的服务器在链路层接收到数据，按序往上层发送，一直到应用层。当传输到应用层，才能算真正接收到由客户端发送过来的HTTP请求。
- 发送端在层与层之间传输数据时，没经过一层时必定会被打上一个该层所属的首部信息。反之，接收端在层与层传输数据时，每经过一层时会把队形的首部消去。
- 这种吧数据信息包装起来的额做法称为封装。
### 1.4 与HTTP关系密切的协议：IP、TCP和DNS
#### IP协议
- IP（Internet Protocol）网际协议位于网络层，几乎所有使用王珞丹额系统都会用到IP协议。TCP/IP协议族中的IP指的就是网际协议，可能有人会把“IP”和“IP地址”搞混，“IP”其实是一种协议的名称。
- IP协议的作用是把各个数据包传送给对方，而要保证确实传送到对方那里，则需要满足各类条件。其中两个重要的条件是IP地址和MAC地址。
- 补充：
    * mac地址：也称为物理地址、硬件地址，存储在设备的EPROM中，长度为48bit，前24位作为组织唯一性标识符，由IEEE分配给各个厂家，比如华为、思科、小米、高通等等，也就是前24位标识设备厂商；后24位厂家自己分配。尽管说mac地址具有唯一性，就如同大家的身份证一样，但还是可以更改的，MAC地址并不能保证唯一性，而且用户可以随意修改电脑的MAC地址，但是并没有影响到相互通信。
    * MAC地址工作在数据链路层，在同一网段的局域网内，通过MAC地址唯一标识一台主机。到了网络层就开始使用IP地址作为主机标识了，通过路由信息找到通信双方，而不是MAC地址。也就是MAC地址的作用范围是一个局域网，在一个局域网内，MAC地址是不能重复的。
    * IP地址同样也是在同一局域网中具有唯一标识性，比如同一路由器下，IP是不可重复的，否则就会产生IP冲突，导致上不了网，当然同一局域网内，如果出现相同的mac地址的话，也会影响联网。
- IP地址指明了节点呗分配到的地址，MAC地址是指网卡所属的固定地址。IP地址可以和MAC地址进行配对。IP地址可变换，但MAC地址基本上不会改变。
- 使用ARP协议凭借MAC地址进行通信：IP间的通信依赖MAC地址。在网络上，通信的双方在同一局域网内的情况是很少的，通常是经过多台计算机和网络设备中转才能连接到对方。而在进行中转时，会利用下一站中转设备的MAC地址来搜索下一个中转目标。这时，会采用ARP协议。ARP协议是一种用以解析地址的协议，根据通信方的IP地址就可以反查出对应的MAC地址；
- 路由选择机制：在到达通信目标前的中转过程中，那些计算机和路由器等网络设备只能获悉很粗略的传输路线。
![IMG_2465.JPG](https://upload-images.jianshu.io/upload_images/1197643-9cd1be9197a13a8e.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
#### TCP协议
- 按层次分，TCP位于传输层，提供可靠的字节流服务。
- 所谓的字节流服务是指，为了方便传输，将大块数据分隔成以报文段为单位的数据包进行管理。而可靠的传输服务是指，能够把数据准确可靠地传给对方。一言以蔽之，TCP协议为了更容易传送大数据才把数据分隔，而且TCP协议能够确认数据最终是否送达到对方。
- 为了确认数据包可以准确无误的送达到对方，TCP 采用三次握手策略。
![IMG_2466.JPG](https://upload-images.jianshu.io/upload_images/1197643-1fb6da104d85a69e.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 第一次握手：建立连接时，客户端发送syn包（syn=j）到服务器，并进入SYN_SENT状态，等待服务器确认；SYN：同步序列编号（Synchronize Sequence Numbers）。
- 第二次握手：服务器收到syn包，必须确认客户的SYN（ack=j+1），同时自己也发送一个SYN包（syn=k），即SYN+ACK包，此时服务器进入SYN_RECV状态；
- 第三次握手：客户端收到服务器的SYN+ACK包，向服务器发送确认包ACK(ack=k+1），此包发送完毕，客户端和服务器进入ESTABLISHED（TCP连接成功）状态，完成三次握手。
#### 补充
- 序列号seq：占4个字节，用来标记数据段的顺序，TCP把连接中发送的所有数据字节都编上一个序号，第一个字节的编号由本地随机产生；给字节编上序号后，就给每一个报文段指派一个序号；序列号seq就是这个报文段中的第一个字节的数据编号。
- 确认号ack：占4个字节，期待收到对方下一个报文段的第一个数据字节的序号；序列号表示报文段携带数据的第一个字节的编号；而确认号指的是期望接收到下一个字节的编号；因此当前报文段最后一个字节的编号+1即为确认号。
- 确认ACK：占1位，仅当ACK=1时，确认号字段才有效。ACK=0时，确认号无效
- 同步SYN：连接建立时用于同步序号。当SYN=1，ACK=0时表示：这是一个连接请求报文段。若同意连接，则在响应报文段中使得SYN=1，ACK=1。因此，SYN=1表示这是一个连接请求，或连接接受报文。SYN这个标志位只有在TCP建产连接时才会被置1，握手完成后SYN标志位被置0。
- 终止FIN：用来释放一个连接。FIN=1表示：此报文段的发送方的数据已经发送完毕，并要求释放运输连接
- PS：ACK、SYN和FIN这些大写的单词表示标志位，其值要么是1，要么是0；ack、seq小写的单词表示序号。
##### 四次挥手过程理解
![20180717204202563.png](https://upload-images.jianshu.io/upload_images/1197643-af7eaa2fa3aa8ee7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 - 第一次挥手：客户端进程发出连接释放报文，并且停止发送数据。释放数据报文首部，FIN=1，其序列号为seq=u（等于前面已经传送过来的数据的最后一个字节的序号加1），此时，客户端进入FIN-WAIT-1（终止等待1）状态。 TCP规定，FIN报文段即使不携带数据，也要消耗一个序号。
- 服务器收到连接释放报文，发出确认报文，ACK=1，ack=u+1，并且带上自己的序列号seq=v，此时，服务端就进入了CLOSE-WAIT（关闭等待）状态。TCP服务器通知高层的应用进程，客户端向服务器的方向就释放了，这时候处于半关闭状态，即客户端已经没有数据要发送了，但是服务器若发送数据，客户端依然要接受。这个状态还要持续一段时间，也就是整个CLOSE-WAIT状态持续的时间。
- 第二次挥手：客户端收到服务器的确认请求后，此时，客户端就进入FIN-WAIT-2（终止等待2）状态，等待服务器发送连接释放报文（在这之前还需要接受服务器发送的最后的数据）。
- 服务器将最后的数据发送完毕后，就向客户端发送连接释放报文，FIN=1，ack=u+1，由于在半关闭状态，服务器很可能又发送了一些数据，假定此时的序列号为seq=w，此时，服务器就进入了LAST-ACK（最后确认）状态，等待客户端的确认。
- 第三次挥手：客户端收到服务器的连接释放报文后，必须发出确认，ACK=1，ack=w+1，而自己的序列号是seq=u+1，此时，客户端就进入了TIME-WAIT（时间等待）状态。注意此时TCP连接还没有释放，必须经过2∗∗MSL（最长报文段寿命）的时间后，当客户端撤销相应的TCB后，才进入CLOSED状态。
- 第四次挥手：服务器只要收到了客户端发出的确认，立即进入CLOSED状态。同样，撤销TCB后，就结束了这次的TCP连接。可以看到，服务器结束TCP连接的时间要比客户端早一些。
#### 常见面试题
- 为什么连接的时候是三次握手，关闭的时候却是四次握手？
    * 因为当Server端收到Client端的SYN连接请求报文后，可以直接发送SYN+ACK报文。其中ACK报文是用来应答的，SYN报文是用来同步的。但是关闭连接时，当Server端收到FIN报文时，很可能并不会立即关闭SOCKET，所以只能先回复一个ACK报文，告诉Client端，"你发的FIN报文我收到了"。只有等到我Server端所有的报文都发送完了，我才能发送FIN报文，因此不能一起发送。故需要四步握手。

- 为什么TIME_WAIT状态需要经过2MSL(最大报文段生存时间)才能返回到CLOSE状态？
    * 虽然按道理，四个报文都发送完毕，我们可以直接进入CLOSE状态了，但是我们必须假象网络是不可靠的，有可以最后一个ACK丢失。所以TIME_WAIT状态就是用来重发可能丢失的ACK报文。在Client发送出最后的ACK回复，但该ACK可能丢失。Server如果没有收到ACK，将不断重复发送FIN片段。所以Client不能立即关闭，它必须确认Server接收到了该ACK。Client会在发送出ACK之后进入到TIME_WAIT状态。Client会设置一个计时器，等待2MSL的时间。如果在该时间内再次收到FIN，那么Client会重发ACK并再次等待2MSL。所谓的2MSL是两倍的MSL(Maximum Segment Lifetime)。MSL指一个片段在网络中最大的存活时间，2MSL就是一个发送和一个回复所需的最大时间。如果直到2MSL，Client都没有再次收到FIN，那么Client推断ACK已经被成功接收，则结束TCP连接。
- 为什么不能用两次握手进行连接？
    * 3次握手完成两个重要的功能，既要双方做好发送数据的准备工作(双方都知道彼此已准备好)，也要允许双方就初始序列号进行协商，这个序列号在握手过程中被发送和确认。
    * 现在把三次握手改成仅需要两次握手，死锁是可能发生的。作为例子，考虑计算机S和C之间的通信，假定C给S发送一个连接请求分组，S收到了这个分组，并发送了确认应答分组。按照两次握手的协定，S认为连接已经成功地建立了，可以开始发送数据分组。可是，C在S的应答分组在传输中被丢失的情况下，将不知道S 是否已准备好，不知道S建立什么样的序列号，C甚至怀疑S是否收到自己的连接请求分组。在这种情况下，C认为连接还未建立成功，将忽略S发来的任何数据分组，只等待连接确认应答分组。而S在发出的分组超时后，重复发送同样的分组。这样就形成了死锁。
- 如果已经建立了连接，但是客户端突然出现故障了怎么办？
    * TCP还设有一个保活计时器，显然，客户端如果出现故障，服务器不能一直等下去，白白浪费资源。服务器每收到一次客户端的请求后都会重新复位这个计时器，时间通常是设置为2小时，若两小时还没有收到客户端的任何数据，服务器就会发送一个探测报文段，以后每隔75秒钟发送一次。若一连发送10个探测报文仍然没反应，服务器就认为客户端出了故障，接着就关闭连接。
###1.5 负责域名解析的DNS服务
- DNS（Nomain Name System）服务是和HTTP协议一样位于应用层的协议。它提供域名到IP地址之间的解析服务。
- 计算机既可以呗赋予IP地址，也可以被赋予主机名和域名。
- 用户通常使用主机名或域名来访问对方的计算机，儿不是直接通过IP地址访问。因为与IP地址的一组纯数字相比，用字母配合数字的表示形式来指定计算机名更符合人类的记忆习惯。
- 但要让计算机去理解名称，相对而言就变得困难了。因为计算机更擅长处理一长串数字。
- 为了解决上述的问题，DNS服务应运而生。DNS协议提供通过域名查找IP地址，或逆向从IP地址反查域名的服务。
![IMG_2467.JPG](https://upload-images.jianshu.io/upload_images/1197643-932cca8a6d0f5df9.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### 1.6 各种协议与HTTP协议的关系![IMG_2468.JPG](https://upload-images.jianshu.io/upload_images/1197643-9c38746880262ac0.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### 1.7 URI和URL
- URI：（Uniform Resource Identifier 共同以资源标识符）
    * Uniform:规定统一的格式可方便处理多种不同类型的资源，二不用根据上下文环境来识别资源指定的访问方式，另外，加入新增的协议方案也更容易；
    * Resource: 资源的定义是“可标识的任何东西”。不近是文档文件，图像或服务等能够区别于其他类型的，全都可作为资源。另外，资源不仅可以是单一的，也可以是多数的集合体；
    * Identifier:标识可标识的对象，也成为标识符；
    * 综上所述，URI就是由某个协议方案标示顿额资源的定位标识符。协议方案是指访问资源所使用的协议类型名称。
    * 采用HTTP协议时，协议方案就是http；
- URL(Uniform Resource Locator)：统一资源定位符，正是使用 Web 浏览器访问 Web 页面时需要输入的网页地址。
- URI 用字符串标识某一互联网资源，而 URL 表示资源的地点（互联网上所处的位置），可见 URL 是 URI 的子集。
- URI格式
    * 表示指定的URI，要使用涵盖全部必要信息的绝对URI、绝对URL以及相对URL。相对URL，是指浏览器中基本URI处指定的URL。
- 绝对URI的格式
![IMG_2471.JPG](https://upload-images.jianshu.io/upload_images/1197643-9502210fc5c887b5.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 使用http：或https：等协议文案名获取访问资源时要指定协议类型。不区分字母大小写，最后附一个冒号；
- 也可使用data：或Javascript：这类指定数据或脚本程序的方案名；
    * 登录信息（认证）
        * 指定用户名和密码作为从服务器端获取资源时必要的登录信息；（可选）
    * 服务器地址
        * 使用绝对URI必须指定带访问的服务器地址。地址可以是类似hackr.jp这种DNS课解析的名称，或是192.168.1.1这类IPv4地址名，还可以是[0:0:0:0:0:0:1]这样用方括号括起来的IPv6地址名。
    * 服务器端口号
        * 指定服务器连接的网络端口号。（可选）若用户省略则自动使用默认端口号
    * 带层次的文件路径
        * 指定服务器上的文件路径来定位特指的资源。这与UNIX体统的文件目录结构相似
    * 查询字符串
        * 针对已指定的文件路径内的资源，可以使用查询字符串传入人以参数（可选）；
    * 片段标识符
        * 使用片段标识符通常可标记出已获取资源中的资资源。但在RFC中并没有明确规定其使用方法（可选）；
- 并不是所有的应用程序都符合RFC
    * 有一个用来制定HTTP协议技术标准的文档，被称为RFC；
    * 通常，应用程序会遵照由RFC确定的标准实现。可以说，FRC是互联网的实际文档，要是不按照RFC标准执行，就有可能导致无法通信的状况。
    * 由于不遵照RFC标准实现就无法进行HTTP协议通信，所以基本上客户端和服务器端都会以RFC为标准来实现HTTP协议，但也存在某些应用恒旭因客户端或吴福气端的不同，而未遵照RFC标准，反而将自称一套的“标准”；
## 第二章 简单的HTTP协议
### 2.1 HTTP协议用于客户端和服务器端之间的通信
- HTTP协议和TCP/IP协议族内的其他众多的协议相同，用于客户端和服务器之间的通信。
- 请求访问文本或图像等资源的一端成为客户端，而提供资源响应的一端称为服务器端。
- 在两台计算机之间使用HTTP协议通信时，在一条通信线路上必定有一段是客户端，另一端则是服务器端。
- 有时候，按实际情况，两台计算机作为客户端和服务器端的角色有可能会互换。但就仅从一条通信路线来说，服务器端和客户端的角色是确定的，而用HTTP协议能够明确区分哪端是客户端，哪端是服务器端。
![IMG_2473.JPG](https://upload-images.jianshu.io/upload_images/1197643-e5c06b8b8bb6ec8b.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- HTTP协议规定，请求从客户端发成，最后服务器端响应该请求并返回。换句话说，肯定是先从客户端开始建立通信的，服务器端在没有接收到请求之前不会发送响应。
- 示例
![IMG_2474.JPG](https://upload-images.jianshu.io/upload_images/1197643-d34bbacca871c889.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 下面则是从客户端发送给某个HTTP服务器端的请求报文中的内容。
![IMG_2587.jpg](https://upload-images.jianshu.io/upload_images/1197643-176fb700816101a0.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 起始行开头的GET表示请求访问服务器的类型，成为方法；
- 随后的字符串/index.html指明了请求访问的资源对象，也叫做请求URI；
- 最后的HTTP/1.1，即HTTP的版本号，用来提示客户端使用的HTTP协议功能；
- 综合来看，这段请求内容的意思是：请求访问某个HTTP服务器上的/index.html页面资源。
- 请求报文是有请求方法、请求URI、协议版本、可选的请求受不字段和内容实体构成的。
![IMG_2475.JPG](https://upload-images.jianshu.io/upload_images/1197643-3f0d7104a5d467e8.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 接收到请求的服务器，会将请求内容的粗粒结果以响应的形式返回。
![IMG_2588.jpg](https://upload-images.jianshu.io/upload_images/1197643-ad88a0e58e3e876c.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 在起始行开头的HTTP/1.1表示服务器对应的HTTP版本。
- 紧挨着的200 OK表示请求的处理结果是状态码和原因短语；
- 下一行显示了创建响应的日期时间，是首部字段内的一个属性；
- 接着以一空行分隔，之后的内容称为资源实体的主体；
- 响应报文基本上有协议版本、状态码（表示请求成功或失败的数字代码）、用以解释状态码的原因短语、可选的响应受不字段以及实体主体构成；
![IMG_2476.JPG](https://upload-images.jianshu.io/upload_images/1197643-0df17c9678479ff6.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### 2.3 HTTP是不保存状态的协议
- HTTP是一种不保存状态、即无状态协议。HTTP协议自身不对请求和响应之间的通信状态进行保存，也就是说在HTTP这个级别，协议对于发送过的请求或响应都不做持久化处理。
- 使用HTTP协议，每当有新的请求发送时，就UI有对应的新响应产生。协议本身对不保留之前一切的请求或响应报文的信息。这是为了更快地处理大量事务，确保协议的可伸缩性，而特意把HTTP协议设计成如此简单的。
- 可是，随着Web的不断发展，因无状态而导致业务处理变得棘手的情况增多了。HTTP/1.1虽然是无状态协议，但为了实现期望的保持状态功能，于是引入了Cookie技术，有了Cookie再用HTTP协议通信，就可以管理状态了。
### 2.4 请求URI定位资源
- HTTP协议使用URI定位互联网上的资源，正式因为URI的特定功能，在互联网上任意位置的资源都能访问到；
![IMG_2478.JPG](https://upload-images.jianshu.io/upload_images/1197643-50044f75779d9ac5.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 当客户端请求访问资源而发送请求时，URI需要将最为请求报文中的请求URI包含在内，指定请求URI的方式有很多；
![IMG_2479.JPG](https://upload-images.jianshu.io/upload_images/1197643-3050ca44ea2d804a.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 除此之外，如果不是访问特定资源而是对服务器本身发送请求，可以用一个*来代替请求URI。
- 示例：查询HTTP服务器端支持的HTTP方法种类
![IMG_2589.jpg](https://upload-images.jianshu.io/upload_images/1197643-94e6eb39413e7f24.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### 2.5 告知服务器意图的HTTP方法
- GET：获取资源
    * GET方法用来请求访问已呗URI识别的资源，指定的资源经服务器端解析后返回响应内容，也就是说，如果请求的资源是文本，就是保持原样返回；如果是像CGI那样的程序，则返回经过执行后的输出结果；
    * 实例：
![IMG_2481.JPG](https://upload-images.jianshu.io/upload_images/1197643-c211d82789ae320f.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![IMG_2482.JPG](https://upload-images.jianshu.io/upload_images/1197643-847fd9e452b0a715.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- POST：传输实体主体
    * POST方法用来传输实体的主体。
    * 虽然用GET方法也可以传输实体的主体，但一般不用GET方法进行传输，二是用POST方法。虽说POST的功能与GET很相似，但POST的主要目的并不是获取响应的主体内容。
    * 示例：
![IMG_2484.JPG](https://upload-images.jianshu.io/upload_images/1197643-059a84a0465f9fb6.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- PUT：传输文件
    * PUT方法用来传输文件，就像FTP协议的文件上传一样，要求在请求报文的主体中包含文件内容，然后保存到请求URI指定的位置；
    * 但是，鉴于HTTP/1.1的PUT方法自身不带验证机制，任何人都可以上传文件，存在安全性问题，因此一般的Web网站不使用该刚发。若配合Web应用程序的验证机制，或架构设计采用REST标准的同类Web网站，就可能会开发使用PUT方法
    * 实例
![IMG_2486.JPG](https://upload-images.jianshu.io/upload_images/1197643-f1dcb94899dfe204.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- HEAD：获得报文首部
    * HEAD方法和GET方法一样，只是不返回报文主体部分。用于确认URI的有效性及资源更新的额日期时间等。
    * 示例
![IMG_2488.JPG](https://upload-images.jianshu.io/upload_images/1197643-134ff136a42c1eec.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- DELETE：删除文件
    * DELETE方法用来删除文件，是与PUT相反的方法。DELETE方法按请求URI删除指定的资源。
    * 但是，HTTP/1.1的DELETE方法本身和PUT方法一样不带验证机制，所以一般的Web网站也不适用DELETE方法。当配合Web应用程序的验证机制，或遵守REST标准是还是有可能会开放使用的；
    * 实例
![IMG_2490.JPG](https://upload-images.jianshu.io/upload_images/1197643-ce74559684f41fe5.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- OPTIONS：询问支持的方法
    * OPTIONS方法用来查询针对请求URI指定的资源支持的方法；
    * 实例
![IMG_2492.JPG](https://upload-images.jianshu.io/upload_images/1197643-cff4060c0315b5b5.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- TRACE：追踪路径
    * TRACE方法是让Web服务器端将之前的请求通信环回给客户端的方法。
    * 发送请求时，在Max-Forwards首部字段中填入数值，每经过一个服务器端就将该数值减1，当数值刚好减到0时，就停止继续传输，最后接收到请求的服务器端则返回状态码200 OK的响应；
    * 客户端通过TRACE方法可以查询发送出去的请求是怎样呗加工修改、篡改的。这是因为：请求想要连接到源目标服务器可能会通过代理中转，TRACE方法就是用来确认连接过程中发生的一系列操作；
    * 但是，TRace方法本来就不怎么常用，再加上它容易引发XST攻击，通持仓就更不会用到了；
    * 实例
![IMG_2493.JPG](https://upload-images.jianshu.io/upload_images/1197643-6ef0553edb3151a7.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![IMG_2494.JPG](https://upload-images.jianshu.io/upload_images/1197643-655ab01096a9e9c7.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- CONNECT：要求用隧道协议连接的代理
    * CONNECT方法要求在与代理服务器通信时简历隧道，实现用隧道协议进行TCP通信。主要使用SSL和TLS协议把通信内容加密后经网络隧道传输
    * CONNECT方法的格式如下：
![IMG_2590.jpg](https://upload-images.jianshu.io/upload_images/1197643-279064d7219bdf5b.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 实例
![IMG_2496.JPG](https://upload-images.jianshu.io/upload_images/1197643-39f4545312eed0d6.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### 2.6 使用方法下达命令
- 向请求URI指定的资源发送请求报文时，采用成为方法的命令；
- 方法的作用在于，可以指定请求的资源按期望山城某种行为。方法中有GET、POST和HEAD等
![IMG_2497.JPG](https://upload-images.jianshu.io/upload_images/1197643-4a0cbabfe4b369bd.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 下表列出了HTTP/1.0和HTTP/1.1支持的方法，另外，方法名区分大小写，注意，要用大写字母；
![IMG_2498.JPG](https://upload-images.jianshu.io/upload_images/1197643-fd097c922395e150.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### 2.7 持久谅解节省通信量
- HTTP协议的初始版本中，没进行一次HTTP通信就要断开一次TCP连接；
![IMG_2500.JPG](https://upload-images.jianshu.io/upload_images/1197643-427af714c35dce5b.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
#### 持久连接
- 为解决上述TCP连接的问题，HTTP/1.1和一部分的HTTP/1.0相处了持久连接的方法。持久连接的特点是，只要热议一端没有明确提出断开连接，则保持TCP连接状态
![IMG_2499.JPG](https://upload-images.jianshu.io/upload_images/1197643-272065b774fc51c8.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 为解决上述TCP连接的问题，HTTP/1.1和一部分的HTTP/1.0相处了持久连接的方法。持久连接的特点是，只要热议一端没有明确提出断开连接，则保持TCP连接状态
- 持久连接的好处在于减少了tcp连接的重复简历和断开所造成的额外开销，减轻了服务器端的负载。另外，减少开销的那部分时间，是HTTP请求和响应能够更早地结束，这样Web页面的显示速度也就是响应提高了；
- 在HTTP/1.1中，所有的链接默认都是持久连接，但在HTTP/1.0内并未标准化。虽然有一部分服务器通过非标准的手段实现了持久连接，但服务器端不一定能够支持持久连接。毫无疑问，除了服务器端，客户端也需要支持持久连接；
#### 管线化
- 持久连接使得多数请求以管线化方式发送成为可能，从前发送请求后需等待并受到响应，才能发送下一个请求。管线化技术出现后，不用等待响应亦可直接发送下一个请求。
- 这样就能够做到同时并行发送多个请求，而不需要一个姐一个地等待响应了；
![IMG_2502.JPG](https://upload-images.jianshu.io/upload_images/1197643-82955cb84c76af58.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### 2.8 使用Cookie的状态管理
- HTTP是无状态协议，它不对之前发生过的请求和响应的状态进行管理，也就是说，无法根据之前的状态进行本次的请求处理；
- 假设要求登录认证的Web页面本身无法进行状态的管理，那么每次跳转新页面就要再次登录，或者要在每次请求报文中附加参数来管理登录状态。
- 不可否认，无状态协议当然也有它的优点，由于不必保存状态，自然可减少服务器的CPU及内存资源的小号。从另一侧面来说，也正是因为HTTP协议本身是非常简单的，所以才会被应用在各种场景里；
- 保留无状态协议这个特征的同时又要解决类似的矛盾问题，于是引入了Cookie技术，Cookie技术通过在请求和响应报文中写入Cookie信息来控制客户端的状态
- Cookie会根据从服务器端发送的响应报文内的一个叫做Set-Cookie的首部字段信息，通知客户端保存Cookie。当下次客户端再往该服务器发送请求时，客户端会自动在请求报文中加入Cookie值后发送出去。
- 服务器端发现客户端发送古来的Cookie后，会去检查酒精是从哪一个客户端发来的连接请求，然后对比服务器上的记录，最后得到之前的状态信息
- 没有Cookie信息状态下的请求
![IMG_2504.JPG](https://upload-images.jianshu.io/upload_images/1197643-8afc8ddf440caf0a.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 第2次以后（存有Cookie信息状态）的请求
![IMG_2505.JPG](https://upload-images.jianshu.io/upload_images/1197643-434db03d7988144f.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 上图展示了发生Cookie交互的情景，HTTP请求报文和想问报文的内容如下：
    * 请求报文（没有Cookie信息的状态）
![IMG_2592.jpg](https://upload-images.jianshu.io/upload_images/1197643-88f51e61c86010a3.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 响应报文（服务器端生成Cookie信息）
![IMG_2593.jpg](https://upload-images.jianshu.io/upload_images/1197643-6cc430baec50f144.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 请求报文（自动发送保存着的Cookie信息）
![IMG_2594.jpg](https://upload-images.jianshu.io/upload_images/1197643-72a91768302f900c.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
## 第三章 HTTP报文内的HTTP信息
### 3.1 HTTP报文
- 用于HTTP协议交互的信息被称为HTTP报文。请区段的HTTP报文叫做请求报文，响应端的叫做响应报文，HTTP报文本身是由多行数据构成的字符串文本；
- HTTP报文大致可分为报文首部和报文主体两块。两者由最初出现的空行来划分，通常，并不一定要有报文主体
![IMG_2506.JPG](https://upload-images.jianshu.io/upload_images/1197643-c31c56db8b315c42.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### 3.2 请求报文及响应报文的架构
- 请求报文（上）和响应报文（下）的结构
![IMG_2507.JPG](https://upload-images.jianshu.io/upload_images/1197643-584681fe309a6364.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![IMG_2508.JPG](https://upload-images.jianshu.io/upload_images/1197643-5fbe0c5396cd300f.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 请求报文和响应报文的受不内容由一下数据组成：
    * 请求行
        * 包含用于请求的方法，请求URI忽然HTTP版本；
    * 状态行
        * 包含表明响应结果的状态码，原因短语和HTTP版本
    * 首部字段
        * 包含表示请求和响应的各种条件和属性的各类首部
        * 一般由4中首部，分别是：通用首部、请求首部、响应首部和实体首部；
    * 其他
        * 可能包含HTTP的RFC里未定义的首部；
### 3.3 编码提升传输速率
- HTTP在传输数据时可以按照数据原貌直接传输，但也可以在传输过程中通过编码提升传输速率。通过在传输时编码，能有效地处理大量的访问请求。但是，编码的操作需要计算机来完成，因此会消耗更多的CPU等资源；
#### 报文主体和实体主体的差异
- 报文
    * 是HTTP通信汇总的基本单位，由8位组字节流组成，通过HTTP通信传输；
- 实体
    * 作为请求或响应的有效载荷数据被传输，其内容由实体首部和实体主体组成；
- HTTP报文的主体用于传输请求或响应的实体主体
- 通常，报文主体等于实体主体。只有当传输中进行编码操作时，试题主体的内容发生变化，才导致它和报文主体产生差异
#### 压缩传输的内容编码
- 向待发送邮件内增加附件时，为了是邮件容量变小，我们会先用ZIP压缩文件之后，在添加附件发送。HTTP协议中有一种被称为内容编码的功能也能进行类似的操作；
- 内容编码指明应用在实体内容上的编码格式，并保持实体信息原样压缩。内容编码后的实体由客户端接收并负责解码；
![IMG_2509.JPG](https://upload-images.jianshu.io/upload_images/1197643-c84bfec672cae3c6.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 常见的内容编码有以下几种：
    * gzip
    * compress
    * deflate
    * identity
#### 分割发送的分块传输编码
- 在HTTP通信过程中，请求的编码实体资源尚未全部传输完成之前，浏览器无法显示请求页面，在传输大容量数据时，通过把数据分割成多块，能够让刘楠器逐步显示页面，这种把实体主体分块的功能称为分块传输编码；
![IMG_2510.JPG](https://upload-images.jianshu.io/upload_images/1197643-7c2cf3efc23946aa.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 分块传输编码会将实体主体分成多个部分，每一块都会用十六进制来标记块的大小，而实体主体的最后一块会使用“0（CR+LF）”来标记；
- 使用分块传输编码的实体主体会由接收的客户端负责解码，回复到解码钱的实体主体；
- HTTP/1.1中存在一种称为传输编码的机制，它可以在通信时按某种编码方式传输，但只定义作用域分块传输编码中；
### 发送多种数据的多部分对象集合
![IMG_2511.JPG](https://upload-images.jianshu.io/upload_images/1197643-729c967ffcefa398.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 发送邮件时，我们可以在邮件里写入文字并添加多份附件。这是因为采用了MIME机制，它允许邮件处理文本、图片、视频等多个不同类型的数据。例如：图片等二进制数据以ASCII码字符编码的方式指明，就是利用MIME来描述标记数据类型。儿再MIMIE扩展中会使用一种称为多部分对象集合的方法，来容纳多份不同类型的数据。
- 响应地，HTTP协议中也采纳了多部分对象集合，发送的一份报文主体内科含有多类型实体。通常是在图片或文本文件等上传时使用；
- 多部分对象集合包含的对象如下：
    * multipart/form-data
        * 在Web表单文件上传时使用；
![IMG_2615.jpg](https://upload-images.jianshu.io/upload_images/1197643-5fc302aae44b3589.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * multipart/byteranges
        * 状态码206响应报文包含了多个规范的内容时使用；
![IMG_2617.jpg](https://upload-images.jianshu.io/upload_images/1197643-02514599630d8643.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 在HTTP报文中使用多部分对象集合时，需要在头部字段中加上Content-type.
- 使用boundary字符串来划分多部分对象集合指明的各类试题。在boundary字符串指定的各个实体的起始行之前插入“--”标记，而在多部分对象集合对应的字符串的最后插入“--”标记作为结束；
- 多部分对象集合的每个部分类型中，都可以含有首部字段。另外，可以在，某个部分中嵌套使用多部分对象集合。
### 3.5 获取部分内容的范围请求
- 之前，用户不能使用现在这种高速的带宽访问互联网，当时，下载一个尺寸少打的图片或文件就已经很吃力了。如果下载过程中遇到网络中断的情况，那就必须重头开始，为了解决上述问题，需要一种可恢复的机制，所谓恢复是指能从之前下载中断处恢复下载；
- 要实现该功能需要指定下载的实体范围。像这样，指定范围发送的请求佳作范围请求。
- 对一份10000字节大小的资源，如果使用范围请求，可以只请求5001~10000字节的资源；
![IMG_2512.JPG](https://upload-images.jianshu.io/upload_images/1197643-a1f79622d9ab950b.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 执行范围请求时，会用到首部字段Range来指定资源的byte范围。byte范围的指定形式如下：
    * 5001~10000字节
![IMG_2618.jpg](https://upload-images.jianshu.io/upload_images/1197643-78f1728672a14778.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 从5001字节之后全部的
![IMG_2619.jpg](https://upload-images.jianshu.io/upload_images/1197643-d729441316753950.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    * 从一开始到3000字节和5000~7000字节的多重范围
![IMG_2620.jpg](https://upload-images.jianshu.io/upload_images/1197643-92c6961a287e205b.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 针对范围请求，响应会返回状态码为206 Partial Content的响应报文。另外，对于多从范围的范围请求，响应会在首部字段Content-Type表明multipart/byteranges后返回响应报文；
- 如果服务器端无法响应范围请求，则会返回状态码200 OK和完整的实体内容；
### 3.6 内容协商放回最合适的内容
- 同一个Web网站有可能存在多多份相同内容的页面，比如：英文版和中文版的Web页面，它们内容上虽相同，但使用的语言却不同；
- 当浏览器的默认语言为英语或中文，访问相同URI的Web页面时，则会显示对应的英语班或中文版的Web页面。这样的机制称为内容协商；
- 内容协商机制是指客户端和服务器端就响应的资源内容进行交涉，然后提供给客户端最为适合的资源。内容协商会以响应资源的语言、字符集、编码方式等最为判断的基准；
- 包含在请求报文中的某些首部字段就是判断的基准；
    * Accept
    * Acccpt-Charset
    * Accept-Encoding
    * Accept-Language
    * Content-Language
- 内容协商技术与以下3中类型
    * 服务器驱动协商
        * 由服务器端进行内容协商。以请求的首部字段为参考，在服务器端自动处理，但对用户来说，以浏览器发送的信息作为判定的依据，并不一定能筛选出最优内容；
    * 客户端驱动协商
        * 由客户端进行内容协商的方式。用户从浏览器显示的可选项列表中手动选择；还可以利用JavaScript脚本在Web页面上自动进行上述选择。比如按OS的类型或浏览器类型，自行切换成PC版页面或手机版页面；
    * 透明协桑
        * 是服务器驱动和客户端驱动的结合体，是由服务器端和客户端各自进行内容协商的一种方法；
## 第四章 返回结果的HTTP状态码
### 4.1 状态码告知从服务器端返回的请求结果
- 状态码的职责是当客户端向服务器端发送请求时，描述返回的请求结果。借助状态码，用户可以知道服务器端是正常处理了请求，还是出现了错误。
![IMG_2514.JPG](https://upload-images.jianshu.io/upload_images/1197643-4edccb43d4576324.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 状态码如200 OK，以3位数字和原因短语组成；
- 数字中的第一位指定了响应类型，后两位无分类；
- 响应类别有以下五种：
![IMG_2515.JPG](https://upload-images.jianshu.io/upload_images/1197643-d536b991147ab93b.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 只要遵守状态码类别的定义，即使改变RFC2616中定义的状态码，或服务器端自行创建状态码都没问题；
### 4.2 2XX成功
- 2XX的响应结果表明请求被正常处理了；
#### 200 OK
![IMG_2516.JPG](https://upload-images.jianshu.io/upload_images/1197643-296f7d8bd06f2294.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 表示从客户端发来的请求在服务器端被正常处理了；
- 在响应报文内，随状态码一起返回的信息会因方法的不同而发生改变；比如：使用GET方法时，对应请求自愿的额实体会作为响应返回；而使用HEAD方法时，对应请求资源的实体主体不随报文作为响应返回；
#### 204 No Content
![IMG_2517.JPG](https://upload-images.jianshu.io/upload_images/1197643-3f5418158ad95fc5.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 该状态码代码服务器接收的请求已成功处理，但在返回的响应报文中不含实体的主体部分。另外，也不允许返回任何实体的主体。比如：当从浏览器发出请求处理后，返回204响应，那么浏览器显示的页面不发生更新；
- 一般在只需要从客户端往服务器发送信息，而对客户端不需要发送新信息内容的情况下使用；
#### 206 Partial Content
![IMG_2622.JPG](https://upload-images.jianshu.io/upload_images/1197643-53ac71be68635b8b.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 该状态码表示客户端进行了范围请求，而服务器成功执行了这部分的GET请求。响应报文中包含由Content-Range指定范围的实体内容；
### 4.3 3XX重定向
- 3XX响应结果表明浏览器需要执行某些特殊的处理以正确处理请求。
#### 301 Moved Permanently
![IMG_2623.JPG](https://upload-images.jianshu.io/upload_images/1197643-1e8a58a2b2110b52.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 永久性重定向。改状态码表示请求的资源分配了新的URI，以后应使用资源在线所指的URI。也就是说，如果已经把资源对应的URI保存为书签了，这时应该按Location首部字段提示的URI从新保存；
#### 302 Found
![IMG_2624.JPG](https://upload-images.jianshu.io/upload_images/1197643-4e2630184b89c989.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 临时性重定向；改状态码表示请求的资源被分配了新的URI，希望用户能使用新的URI访问；
- 和301 Moved Permanently状态码相似，但302状态码代表的资源不是被永久移动，只是临时性质的，换句话说，已移动的资源对应的URI将来还是有可能发生改变。比如，用户把URI保存成书签，但不会像301状态码出现时那样去更新书签，而是仍旧保留返回302状态码的页面对应的URI；
#### 303 See Other
![IMG_2625.JPG](https://upload-images.jianshu.io/upload_images/1197643-dd5f180ebe85f659.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 该状态码表示由于请求对应的资源存在着另一个URI，应使用GET方法定向获取请求的资源；
- 303状态码和302 Found状态码有着相同的功能，但303状态码明确表示客户端应当采用GET方法获取资源，这点与302状态码有区别；
- 比如，当使用POST方法访问CGI程序，其执行后的处理结果是希望客户端能以GET方法重定向到另一个URI上去时，返回303状态码。虽然302 Found状态码也可以实现相同的功能，但这里使用303状态码是最理想的。
- 注：当301、302、303响应状态码返回时，几乎所有的浏览器都会把POST改成GET，并删除请求报文内的主体，之后请求会自动再次发送；301、302标准是禁止将POST方法改变成GET方法的，但实际使用时大家都会这么做；
#### 304 Not Modified
![IMG_2626.JPG](https://upload-images.jianshu.io/upload_images/1197643-45da48c37c019512.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 该状态码表示客户端发送附带条件的请求时，服务器端允许请求访问资源，但因发生请求未满足条件的情况后，直接返回304 Not Mondified；304状态码返回时，不包含任何响应的主体部分。304虽然被划分在3XX类别中，但是和重定向没有关系
#### 305 Temporary Redirect
- 临时重定向。该状态码与302 Found有着相同的含义。尽管302标准禁止POST变换成GET，但实际使用时大家并不遵守；
- 307会遵照浏览器标准，不会从POST变成GET。但是，对于处理响应时的行为。每种浏览器有可能出现不同的情况；
### 4.4 4XX客户端错误
- 4XX的响应结果表明客户端是发生错误的原因所在；
#### 400 Bad Request
![IMG_2627.JPG](https://upload-images.jianshu.io/upload_images/1197643-5ecf6a094a26c7d1.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 该状态码表示请求报文中存在语法错误。当错误发生时，需修改请求的内容后再次发送请求。另外，浏览器会像200 OK一样对待该状态码
#### 401 Unauthorized
![IMG_2628.JPG](https://upload-images.jianshu.io/upload_images/1197643-c5143b340f29deae.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 该状态码表示发送的请求需要有同感HTTP认证的认证信息。另外若之前已进行过1次请求，则表示用户认证失败；
- 返回含有401的响应必须包含一个适用于被请求自愿的WWW-Authenticate首部用以质询用户信息。当浏览器初次接收到401响应，会弹出认证用的对话窗口；
#### 403 Forbidden
![IMG_2629.JPG](https://upload-images.jianshu.io/upload_images/1197643-43dbc381152ff499.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 该状态码表明对请求资源的访问被服务器拒绝了。服务器端没有必要给出拒绝的详细理由，但如果想作说明的话，可以在实体的主体部分对原因进行描述，这样就能让用户看到了；
- 未获得文件系统的访问授权，访问权限出现某些问题等列举的情况都可能是发生403的原因；
#### 404 Not Found
![IMG_2630.JPG](https://upload-images.jianshu.io/upload_images/1197643-bdd6b7cfa8f37de9.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 该状态码表明服务器上无法找到请求的资源。吹之外，也可以在服务器端拒绝请求且不想说明理由时使用；
- 5XX的响应结果表明服务器本身发生错误；
#### 500 Internal Server Error
![IMG_2631.JPG](https://upload-images.jianshu.io/upload_images/1197643-d098c8efa1ec6fe7.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 该状态码表明服务器端在执行请求时发生了错误。也有可能是Web应用存在的bug或某些临时的故障；
#### 503 Service Unavailable
![IMG_2632.JPG](https://upload-images.jianshu.io/upload_images/1197643-37878583b163e2f1.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 该状态码表明服务器暂时处于超负载或正在进行停机维护，现在无法处理请求。如果事先得知解除以上状况需要的时间，最好写入Retry-After首部字段再返回给客服端。
- 注意：状态码和状况的不一致：不少返回的状态码响应都是错误的，但是用户可能察觉不到这点。比如Web应用程序内容发生错误，状态码依然返回200 OK，这种情况也经常遇到；
## 第五章 与HTTP协作的Web服务器
### 5.1用单台虚拟主机实现多个域名
- HTTP/1.1规范允许一台HTTP服务器搭建多个Web站点。比如，提供Web托管服务的供应商，可以用一台服务器为多个客户服务，也可以以每位客户持有的域名运行各自不同的网站。这是因为利用了虚拟主机的功能；
- 即使物理层面只有一台服务器，但只要使用虚拟主机的功能，则可以假想已具有多台服务器。
![IMG_2633.JPG](https://upload-images.jianshu.io/upload_images/1197643-04679a4613f7101f.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 客户端使用HTTP协议访问服务器时，会经常采用类似www.hackr.jp这样的主机名和域名；
- 在互联网上，域名通过DNS服务映射到IP地址之后反问目标网站。可见，当请求发送到服务器时，已经是以IP地址形式访问了；
- 所以，如果一台服务器内托管了www.teicorder.jp和www.hackr.jp这两个域名，当收到请求时就需要弄清楚究竟要访问哪个域名
![IMG_2634.JPG](https://upload-images.jianshu.io/upload_images/1197643-1870cfe9c153aa5b.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 在相同的IP地址下，由于虚拟主机可以寄存多个不同主机名和域名的Web网站，因此在发送HTTP请求时，必须在Host首部内完整指定主机名或域名的URI；
### 5.2 通信数据转发程序：代理、网关、隧道
- HTTP通信时，除哭护短和服务器以外，还有一些用于通信数据转发的应用程序，例如代理、网关和隧道；他们可以配合服务器工作；
- 这些应用程序和服务器可以将请求转发给通信线路上的下一站服务器，并且能接受从那台服务器发送的响应再转发给客户端；
- 代理
    * 代理是一种有转发功能的应用程序，它扮演了位于服务器和客户端“中间人”的角色，接收由客户端发送的请求并转发给服务器，同时也接收服务器返回的响应并转发给客户端；
- 网关
    * 网关是转发其他服务器通信数据的服务器，接收从客户端发送来的请求时，他就像自己拥有资源的源服务器一样对请求进行处理。有时客户端可能都不会察觉，自己的通信目标是一个网关。
- 隧道
    * 隧道是在相隔甚远的客户端和服务器两者之间进行中转，并保持双方通信连接的应用程序；
#### 代理
![IMG_2635.JPG](https://upload-images.jianshu.io/upload_images/1197643-0db342371169b6da.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 代理服务器的基本行为就是接收客户端发送的请求后转发给其他服务器，代理不改变请求URI，会直接发送给前方持有资源的目标服务器；
- 持有资源实体服务器被称为源服务器。从源服务器返回的响应经过代理服务器后再传给客户端
![IMG_2636.JPG](https://upload-images.jianshu.io/upload_images/1197643-5b4c1cc85485c2b9.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 在HTTP通信过程中，可级联多态代理服务器。请求和响应的转发给经过数台类似锁链一样连接起来的代理服务器。转发时，需要附加Via首部字段以标记出经过的主机信息；
![IMG_2637.JPG](https://upload-images.jianshu.io/upload_images/1197643-e41e6063bf51ce4a.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 使用代理服务器的理由有：利用缓存技术减少网络带宽的流量，组织内部针对特定网站的访问控制，以获取访问日志为主要目的，等等；
- 代理有多重使用方法，按两种基准分类，一种是是否使用缓存，另一种是是否会报修报文。
##### 缓存代理
- 代理转发响应时，缓存代理会预先将资源的副本保存在代理服务器上；
- 当代理再次接收到对相同资源的请求时，就可以不从源服务器那里获取资源，而是将之前缓存的资源作为响应返回
##### 透明代理
- 转发请求或响应时，不对报文做任何加工的代理类型被称为透明代理，反之，对报文内容进行加工的代理被称为非透明代理。
#### 网关
![IMG_2638.JPG](https://upload-images.jianshu.io/upload_images/1197643-4fa9fab2c041b2b6.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 网关的工作机制和代理十分相似，而网关能使通信线路上的服务器提供非HTTP协议服务；
- 利用网关能提高通信的安全性，因为可以在客户端与网关之间的通信线路上加密以确保连接的安全。比如：网关可以连接数据库，使用SQL语句查询数据。另外，在Web购物网站上进行信用卡结算时，网关可以和信用卡结算系统联动；
#### 隧道
- 隧道可按要求建立起一条与一塔服务器的通信线路，届时使用SSL等加密手段进行通信。隧道的目的是确保哭护短能与服务器进行安全的通信。
- 隧道本身不会去解析HTTP请求。也就是说，请求保持原样中转给之后的服务器，隧道会在通信双方断开连接时结束。
![IMG_2639.JPG](https://upload-images.jianshu.io/upload_images/1197643-af804133b3764a22.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### 5.3 保持资源的缓存
- 缓存是指代理服务器或客户端本地磁盘内保存的资源副本。利用缓存可减少对源服务器的访问，因此也就节省了通信流量和通信时间。
- 缓存服务器是代理服务器的一种，并归类在缓存代理类型中。换句话说，当代理转发从服务器返回的响应时，代理服务器将会保存一份资源的副本；
![IMG_2640.JPG](https://upload-images.jianshu.io/upload_images/1197643-94706b26aad61f3d.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 缓存服务器的优势在于利用缓存可避免多次从原服务器转发资源。因此客户端可就近从缓存服务器上获取资源，而源服务器也不必多次处理相同的请求了。
#### 缓存的有效期限
- 即便缓存服务器内有缓存，也不能保证每次都会返回对通资源的请求。因为这关系到被缓存资源的有效性问题。
- 当遇上源服务器上的资源更新时，如果还是使用不变的缓存，那就会演变成返回更新前的“旧”资源了；
- 即使存在缓存，也会因为客服端的要求、缓存的有效期等因素，向源服务器确认资源的有效性。若判断缓存失效，缓存服务器将会再次从源服务器上获取“新资源”
![IMG_2641.JPG](https://upload-images.jianshu.io/upload_images/1197643-515dfb7ae2558385.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
#### 客户端的缓存
- 缓存不仅可以存在于缓存服务器内，还可以存在客户端浏览器中。以Internet Explorer程序为例，把客户端缓存称为临时网络文件；
- 浏览器缓存如果有效，就不必再向服务器请求相同的资源了，可以直接从本地磁盘内读取；
- 另外，和缓存服务器相同的一点是，当判定缓存过期后，会向源服务器确认资源的有效性。若判断浏览器缓存失效，浏览器会再次请求新资源；
![IMG_2642.JPG](https://upload-images.jianshu.io/upload_images/1197643-6bb7d79b75fc5bb6.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

