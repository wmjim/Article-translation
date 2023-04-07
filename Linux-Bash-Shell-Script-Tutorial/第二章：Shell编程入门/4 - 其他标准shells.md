# 其它标准 shells

在 Linux 中，很多工作都是用命令行 shell 完成的。Linux 预装了 Bash 。在 Linux 下还有许多其他的 shell 可用：

- tcsh —— csh 的一个增强版，即C shell。
- ksh —— 真正的、AT&T 版本的 Korn shell
- csh —— 具有类似 C 语言语法的外壳，BSD 系统上的标准登录外壳。
- zsh —— 一个强大的交互式 shell。
- scsh —— 一个嵌入 Scheme 编程语言的开源 Unix shell。

## 找出可用的二进制包 shell 列表

要找到 Red Hat Enterprise Linux / CentOS Linux / Fedora Linux 下可用的 shell 软件包列表，请输入：

``` bash
yum search shell
```

要找到 Debian Linux / Ubuntu Linux 下可用的 shell 软件包列表，请输入：

``` bash
apt-cache search shell
```

## 有效登录 shell 的路径名

`/etc/shells` 是一个文本文件，包含了有效 `shells` 的完整路径名。这个文件可以被 chsh 查询，也可以被其他程序如 ftp 服务器查询。

``` bash
cat /etc/shells
```

样例输出：

``` bash
/bin/sh
/bin/bash
/sbin/nologin
/bin/tcsh
/bin/csh
/bin/zsh
/bin/ksh
```

### 哪一个命令

你也可以使用 which 命令来显示（shell）命令的完整路径：

``` bash
which commandname
which bash
```
样例输出：

``` bash
/bin/bash
```

对于它的每一个命令行参数，它都会向 stdout（屏幕）打印可执行文件的完整路径，如果在 shell 提示符下输入该参数，就会执行该文件：

``` bash
which date
which gcc
which vim
```

样例输出：

``` bash
/usr/bin/date
/usr/bin/gcc
/usr/bin/vim
```

然而，它不能告诉你在所有情况下 shell 将执行什么，因为它是一个外部命令。为了获得更准确的信息，请使用下面的 type 命令：

``` bash
type -p commandName
type -p bash
type -p date
type -p gcc
type -p echo
```

样例输出：

``` bash
/usr/bin/bash
/usr/bin/date
/usr/bin/gcc
```