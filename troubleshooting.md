# Linux 故障排除速查表：starce，htop，lsof，tcpdump，iftop，sysdig
> 翻译至：https://sysdig.com/blog/linux-troubleshooting-cheatsheet/

> 这是一份Linux管理员故障排除的命令行速查表，对深入分析他们的服务器有很大的帮助；无论你是一个工作一个月的新手还是一个工作20年的高手，这里肯定会有一个你所钟爱的工具来帮助你解决问题。

### strace
> `strace`和`sysdig`之间有一个微妙的差异，特别是在许多并行的程序（环境）中比较明显，比如一些简单的`strace`例子中包括可执行的命令行和一次性的操作，表现非常突出；
而在其它方面，`sysdig`却有一个不同的理念，因为它发生的事件是实时监控的，它会在分析并捕获数据之前保存到一个文件中去。值得庆幸的是，`sysdig`提供了丰富
的过滤选项来监视一次性的操作，下面的你将会看到：

![](picture/1.png)
