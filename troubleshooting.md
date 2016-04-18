# Linux 故障排除速查表：starce，htop，lsof，tcpdump，iftop，sysdig
> 翻译至：https://sysdig.com/blog/linux-troubleshooting-cheatsheet/

> 这是一份Linux管理员故障排除的命令行速查表，对深入分析他们的服务器有很大的帮助；无论你是一个工作一个月的新手还是一个工作20年的高手，这里肯定会有一个你所钟爱的工具来帮助你解决问题。

### strace
> `strace`和`sysdig`之间有一个微妙的差异，特别是在许多并行的程序（环境）中比较明显，比如一些简单的`strace`例子中包括可执行的命令行和一次性的操作，表现非常突出；
而在其它方面，`sysdig`却有一个不同的理念，因为它发生的事件是实时监控的，它会在分析并捕获数据之前保存到一个文件中去。值得庆幸的是，`sysdig`提供了丰富
的过滤选项来监视一次性的操作，下面的你将会看到：

<table>
  <tr>
    <th>Operation</th>
    <th>strace</th>
    <th>sysdig</th>
    <th>Note</th>
  </tr>
  <tr>
    <td>跟踪命令的执行</td>
    <td>strace who</td>
    <td>sysdig proc.name=who</td>
    <td>在这里`strace`运行的`who`命令是一次性的，而`sysdig`会监视`who`命令的执行；使用`sysdig`过滤功能来隔离指定的例子：`sysdig proc.name=who and proc.ppid=534`，这将会在shell中间是`who`命令的执行，并且`PID`为534</td>
  </tr>
</table>