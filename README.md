# v2ray
官网:http://v2ray.com(被墙)
请遵守法律！
# Project V
Project V 是一个工具集合，它可以帮助你打造专属的基础通信网络。Project V 的核心工具称为V2Ray，其主要负责网络协议和功能的实现，与其它 Project V 通信。V2Ray 可以单独运行，也可以和其它工具配合，以提供简便的操作流程。
# v2ray是什么？
V2Ray 是 Project V 下的一个工具。Project V 是一个包含一系列构建特定网络环境工具的项目，而 V2Ray 属于最核心的一个。 官方中介绍Project V 提供了单一的内核和多种界面操作方式。内核（V2Ray）用于实际的网络交互、路由等针对网络数据的处理，而外围的用户界面程序提供了方便直接的操作流程。不过从时间上来说，先有 V2Ray 才有 Project V。 如果还是不理解，那么简单地说，V2Ray 是一个与 Shadowsocks 类似的代理软件，可以用来科学上网（翻墙）学习国外先进科学技术。
V2Ray 用户手册：https://www.v2ray.com（已被墙） https://v2ray.cool（已被墙）
V2Ray 项目地址：https://github.com/v2ray/v2ray-core
V2Ray Telegram 使用群链接：https://t.me/projectv2ray
V2Ray 跟 Shadowsocks 有什么区别？
区别还是有的，Shadowsocks 只是一个简单的代理工具，而 V2Ray 定位为一个平台，任何开发者都可以利用 V2Ray 提供的模块开发出新的代理软件。
了解 Shadowsocks 历史的同学都知道，Shadowsocks 是 clowwindy 开发的自用的软件，开发的初衷只是为了让自己能够简单高效地科学上网，自己使用了很长一段时间后觉得不错才共享出来的。V2Ray 是 clowwindy 被喝茶之后 V2Ray 项目组为表示抗议开发的，一开始就致力于让大家更好更快的科学上网。

由于出生时的历史背景不同，导致了它们性格特点的差异。

简单来说，Shadowsocks 功能单一，V2Ray 功能强大。听起来似乎有点贬低 Shadowsocks 呢？当然不！换一个角度来看，Shadowsocks 简单好上手，V2Ray 复杂配置多。

# 既然 V2Ray 复杂，为什么要用它？
童鞋，某事物的优点和缺点总是相生相随的。相对来说，V2Ray 有以下优势：

更完善的协议: V2Ray 使用了新的自行研发的 VMess 协议，改正了 Shadowsocks 一些已有的缺点，更难被墙检测到
更强大的性能: 网络性能更好，具体数据可以看 V2Ray 官方博客
更丰富的功能: 以下是部分 V2Ray 的功能
mKCP: KCP 协议在 V2Ray 上的实现，不必另行安装 kcptun
动态端口：动态改变通信的端口，对抗对长时间大流量端口的限速封锁
路由功能：可以随意设定指定数据包的流向，去广告、反跟踪都可以
传出代理：看名字可能不太好理解，其实差不多可以称之为多重代理。类似于 Tor 的代理
数据包伪装：类似于 Shadowsocks-rss 的混淆，另外对于 mKCP 的数据包也可伪装，伪装常见流量，令识别更困难
WebSocket 协议：可以 PaaS 平台搭建V2Ray，通过 WebSocket 代理。也可以通过它使用 CDN 中转，抗封锁效果更好
Mux:多路复用，进一步提高科学上网的并发性能
# 哪有十全十美的东西？
少年悟性很高啊！当然没有！目前来说，V2Ray 有下面的缺点：

配置复杂
产业链不成熟

由于许多 V2Ray 用户都有使用过 Shadowsocks 的经验，基本上可以按照使用 Shadowsocks 那样使用。但是 V2Ray 还是和 Shadowsocks 不太一样，所以我大概说一下使用上的差异。请注意，差异不代表好坏或优劣，如果一个事物必须拥有其他同类所拥有的东西，那么它也就没有了存在的意义。

客户端：V2Ray 本身只是一个内核，V2Ray 上的图形客户端大多是调用 V2Ray 内核套一个图形界面的外壳，类似于 Linux 内核和 Linux 操作系统的关系；而 Shadowsocks 的客户端都是自己重新实现了一遍 Shadowsocks 协议。本文的内容短期内不涉及图形客户端的使用。
分流：也许大家第一反映是 PAC，实际上无论是 Shadowsocks (特指 Shadowsocks-libev) 还是 V2Ray 本身不支持 PAC，都是客户端加进来的；Shadowsocks 的分流使用 ACL，V2Ray 使用自己实现的路由功能，孰优孰劣只是仁者智者的问题。
分享链接/二维码：V2Ray 不像 Shadowsocks 那样有统一规定的 URL 格式，所以各个 V2Ray 图形客户端的分享链接/二维码不一定通用。
加密方式：V2Ray (特指 VMess 协议) 不像 Shadowsocks 那样看重对加密方式的选择，并且 VMess 的加密方式是由客户端指定的，服务器自适应。
时间：使用 V2Ray 要保证时间准确，因为这是为了安全设计的。
密码：V2Ray(VMesss) 只有 id（使用 UUID 的格式），作用类似于 Shadowsocks 的密码，但随机性远好于 Shadowsocks 的密码，只是不太方便记忆(安全和方便的矛盾)。
UDP 转发：VMess 是基于 TCP 的协议，对于 UDP 包 V2Ray 会转成 TCP 再传输的，即 UDP over TCP。要 UDP 转发功能在客户端的 socks 协议中开启 UDP 即可。
路由器翻墙：实际上它们并没有什么区别，不要以为没有插件就不能在路由器上用，看事物请看本质。
