# 什么是 Linux Shell

计算机理解 0 和 1 的语言，被称为二进制语言。在计算的早期，指令是用二进制语言提供的，这对我们所有人来说都很难读和写。因此，一个操作系统有一个独特的程序，称为 shell 。shell 接受人类可读的命令，并将它们翻译成内核可以阅读和处理的东西。

## 什么是一个 Shell?

- Shell 是一个用户程序，或者说它是为用户互动提供的环境
- 它是一个命令语言解释器，执行从标准输入设备如键盘或文件中读取的命令
- 当你登录或打开一个控制台（终端）时，shell 就会启动
- 快速和肮脏（打开的进程多）的方式来执行实用程序
- shell 不是系统内核的一部分，但它使用系统内核来执行程序、创建文件等
- 有几种可用于 Linux 的 shell，包括：
  - BASH（Bourne-Again SHell）--Linux 中最常见的 Shell，它是开源的
  - CSH (C SHell) - C shell 的语法和用法与 C 编程语言非常相似
  - KSH（Korn SHell）--由 David Korn 在 AT&T 贝尔实验室创建。Korn Shell 也是 POSIX Shell 标准规范的基础
  - TCSH - 它是 Berkeley UNIX C shell (CSH) 的一个增强但完全兼容的版本。

> 请注意，每个 shell 都做同样的工作，但每个 shell 都理解不同的命令语法并提供不同的内置功能。在 MS-DOS 下，shell 的名字是 COMMAND.COM，它也用于相同的目的，但它到目前为止还不如我们的 Linux Shell 强大

### Shell 提示符

有各种各样的方法来获得 Shell 权限：

- **Terminal** - Linux 桌面提供了一个基于 GUI 的登录系统。一旦登录，你可以通过运行 X 终端（XTerm）、Gnome 终端（GTerm）或 KDE 终端（KTerm）应用程序来获得对外壳的访问
- **通过安全 Shell（SSH）连接** - 当你登录到远程服务器或工作站时，你会得到一个 Shell 提示符
- **使用 console** - 少数 Linux 系统还提供了一个基于文本的登录系统。一般来说，你一登录到系统中就会得到一个 shell 提示

## 我怎样才能知道我目前的 Shell 名称？

要找到你系统中所有可用的 shell，请输入以下命令：

```bash
cat /etc/shells
```

![/etc/shells 是一个文本文件，它包含有效登录shells的完整路径名。](https://gitee.com/mengwg/my_pictures/raw/master/img/202304061934886.png)

如果 /etc/shells 文件中列出了一个以上的 shell，那么这意味着你的平台支持一个以上的 shell。

### 与 Bourne 兼容的 shells

1. bash
2. ksh
3. sh
4. zsh

### 兼容 C 型 Shell 的 Shells

1. bcsh
2. csh
3. tcsh

### 命令行接口（CLI）

shell 为 Linux 提供了一个界面，在这里你可以使用键盘键入或输入命令。它被称为命令行界面（CLI）。要想知道你当前的 shell，请键入以下命令^[1]^：

```bash
echo $SHELL
ps $$
ps -p $$
```

下面的样本输出表明我在使用 bash shell：

![image-20230406193934396](https://gitee.com/mengwg/my_pictures/raw/master/img/202304061939440.png)

### 基本的命令行编辑

你可以使用以下组合键来编辑和调用命令：

- CTRL + L : 清除屏幕。
- CTRL + W : 删除从光标开始的单词。
- CTRL + U : 清除该行，即删除命令行中的所有字。
- 向上和向下箭头键：调用命令（见命令历史）。
- Tab键：自动完成文件、目录、命令名称和更多。
- CTRL + R : 搜索以前使用的命令（见命令历史）。
- CTRL + C : 取消当前运行的命令。
- CTRL + T : 交换光标前的最后两个字符。
- ESC + T : 交换光标前的最后两个单词。
- CTRL + H : 删除从光标开始的字母。



### 执行一个命令

输入你的命令，然后按回车键。试试这个日期命令，它将显示当前的日期和时间：

```bash
date
```

样本输出

```bash
2023年 04月 06日 星期四 19:42:58 CST
```

### 命令和文件完成情况

Bash shell 会在可能的情况下或当你告诉他们时，自动完成文件和命令的名称。例如，如果你输入**`sle`**并按下 Tab 键将使 Shell 自动完成你的命令名称。另一个例子，如果你输入**`ls /e`**并按下 Tab 键，shell 会自动完成你对**`/etc`**的描述，因为它看到**`/etc/`**是一个以**`/e`**开头的目录。

### 在 Linux 中获得帮助

- Linux下的大多数命令都会有文档
- 你可以用 `man` 命令或 `info` 命令查看文档。在这个例子中，打开 date 命令的 man 页：

```bash
man date
```

- 你可以按以下方式阅读 ls 命令的信息文档：

``` bash
info ls
```
- 许多命令接受 `--help` 或` -h  `命令行选项。在这个例子中，显示 date 命令的帮助选项：

``` bash
date --help
```

- 你可以使用 `help` 命令来显示关于内置命令的信息。例如，请看关于 set builtin 命令的帮助：
``` bash
help set
```
- 简而言之，使用以下任何一个选项来获得更多关于 Linux 命令的信息：
``` bash
man commandName
info commandName
commandName -h
commandName --help
```

## 引用

1. [查出当前 shell 名称的命令](https://www.cyberciti.biz/tips/how-do-i-find-out-what-shell-im-using.html) 来自 nixCraft 的 FAQ 部分
