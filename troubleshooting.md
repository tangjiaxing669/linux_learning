# Linux 故障排除速查表：starce，htop，lsof，tcpdump，iftop，sysdig
> 翻译至：https://sysdig.com/blog/linux-troubleshooting-cheatsheet/

> 这是一份Linux管理员故障排除的命令行速查表，对深入分析他们的服务器有很大的帮助；无论你是一个工作一个月的新手还是一个工作20年的高手，这里肯定会有一个你所钟爱的工具来帮助你解决问题。

### strace
> `strace`和`sysdig`之间有一个微妙的差异，特别是在许多并行的程序（环境）中比较明显，比如一些简单的`strace`例子中包括可执行的命令行和一次性的操作，表现非常突出；
而在其它方面，`sysdig`却有一个不同的理念，因为它发生的事件是实时监控的，它会在分析并捕获数据之前保存到一个文件中去。值得庆幸的是，`sysdig`提供了丰富
的过滤选项来监视一次性的操作，下面的你将会看到：

![](picture/1.png)

### htop
> `htop`是一个实时的、和交互式的工具，我们可以把它比作一个可实时交互的`csysdig`。对于初学者来说，这两种工具有着相同的使用导向，`上/下/左/右`箭头以及`PgUp`键和`PgDn`键。

![](picture/2.png)

### lsof

![](picture/3.png)

### tcpdump
> `tcpdump`完全集中于网络通信，而对于`sysdig`，网络流量只是它的一个子集。许多`tcpdump`的使用案列都涉及到过滤和使用特定网络`BPF`过滤器，而`sysdig`则使用自己的更为广泛的`sysdig`过滤功能；这两种方法看起来有许多的相似，但当你有更为苛刻的过滤功能的时候，你会想到这两者的区别。

![](picture/4.png)

### iftop
> iftop是一个可交互的工具，有点类似csysdig；

![](picture/5.png)

> 官方地址：https://sysdig.com/
