# bash shell

Bash 是 Linux 操作系统的 shell 或命令语言解释器。这个名字是 Bourne-Again SHell 的缩写，是对 Stephen Bourne 的双关语，他是目前 Unix shell 的直接祖先 sh 的作者，出现在第七版贝尔实验室研究版的 Unix Bash 参考手册中^[1]^。

## Bash Shell简介

命令行是一个文本用户接口。人们可以使用这样的界面来向由 Linux 驱动的计算机提供指令。在 Linux 下，一个叫做 shell 的程序用来提供 Linux 命令行用户界面。 Linux 中用户的默认 shell 是 GNU bash：

- 由 GNU 项目开发
- 大多数 Linux 发行版上的默认 Linux shell
- 向后兼容原始的 sh UNIX shell
- Bash 在很大程度上与 sh 兼容，并结合了 Korn shell ksh 和 C shell csh 的有用功能
- Bash 是 Linux 的默认外壳。然而，它确实可以在每个版本的Unix和其他一些操作系统上运行，如 ms-dos、os/2 和 Windows 平台

*引自 Bash 的官方主页：*

> Bash 是将出现在 GNU 操作系统中的 shell，或命令语言解释器。它旨在符合 IEEE POSIX P1003.2/ISO 9945.2 shell 和工具标准。它在编程和交互式使用方面都比 sh 有功能上的改进。此外，大多数sh脚本可以由Bash运行而不需要修改。

### 命令（shell）提示

通常情况下，当 bash 在等待用户的命令时，你会看到一个`$`提示。这就是所谓的命令提示符或shell提示符。对于普通用户来说，默认的命令提示符以`$`结束，而对于根用户来说，默认的提示符以`#`结束。

![The default command (shell) prompt for a regular and root user](https://gitee.com/mengwg/my_pictures/raw/master/img/202304070933472.png)

### BASH 提供的改进措施包括：

Bash 语法是 Bourne shell 语法的一个改进版本。在大多数情况下，Bourne shell 脚本可以被 Bash 执行而没有任何问题。

- 命令行编辑
- 命令行完成
- 无限大小的命令历史
- 提示符控制
- 无限大小的索引数组（Arrays）
- 从二到六十四的任何基数的整数运算
- Bash 启动文件 - 你可以将 bash 作为一个交互式登录 shell 或交互式非登录 shell 运行。参见 Bash 启动文件以了解更多信息。
- Bash 条件表达式： 用于组成测试内置或 `[[` 或 `]` 命令的各种表达式
- 目录堆栈 - 访问过的目录的历史
- 限制性 Shell： 一种更受控制的 Shell 执行模式
- Bash POSIX 模式： 使 Bash 的行为更接近于 POSIX 标准所规定的

### Bash v4.0 特色

- 常用的运行时环境： POSIX
- 命令和文件名填写 - Bash 可以自动填写部分输入的命令或命令的参数，如文件名、主机名等等
- 运算支持：
  - 支持整数算术
  - 不支持浮点算术
  - 指数符号通过 printf 内建程序进行限制
  - 不支持日期和时间算术
- 哈希表： Bash 使用一个哈希表来记忆可执行文件的完整路径名
- 支持模式匹配和正则表达式
- Globbing - 例如，你可以使用 `*.conf` 来匹配 `/etc` 目录下所有的 `conf` 文件
- 通过 pushd 和 popd 内置支持目录栈
- Bash 完全支持命令历史和历史完成
- 自定义命令提示 - 允许你改变默认的提示



## 作者

- Brian J. Fox 在1987年编写了 GNU Bash shell。
- Fox 作为 Bash 的主要维护者一直维护到 1993 年，这时 Chet Ramey 接手了。
- Chet Ramey 是目前 GNU Bourne Again Shell 和 GNU Readline 的维护者。

### 下载 Bash Shell

Bash 是 Linux 下的默认外壳。目前的生产版本是 Bash 3.x 和 4.x ，你可以从[官方网站](http://ftp.gnu.org/gnu/bash/)上获取。

## 外部链接

- [Bash home page](http://www.gnu.org/software/bash/bash.html)
- [Chet's home page](http://cnswww.cns.cwru.edu/php/chet/)

## 引用

1. [[1]](https://bash.cyberciti.biz/guide/The_bash_shell#cite_ref-1) Bash参考手册