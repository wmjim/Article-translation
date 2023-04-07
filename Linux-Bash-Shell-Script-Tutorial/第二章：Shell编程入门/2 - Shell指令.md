# Shell 指令

bash shell有两种类型的命令：

- [内部命令](https://bash.cyberciti.biz/guide/Internal_commands) (builtins) - 这些类型的命令内置于 shell 本身。shell 本身的一部分，即内置于 shell 中。
- [外部命令](https://bash.cyberciti.biz/guide/External_commands) - 外部命令是指存储在以下目录中的独立程序：
  - `/bin`
  - `/usr/bin`
  - `/usr/local/bin`
  - `/sbin`
  - `/usr/sbin`
  - `/usr/local/sbin`

## 使用Bash Shell执行命令

正如前面所解释的，bash 解释用户在 `$` 提示符下输入的命令。输入到 bash 中的每个文本可能有三个部分：

1. 命令
2. 通常以 `-` 或 `——` 开头的选项
3. 参数

确保输入到 bash 中的每个单词都用空格隔开。比如说：

``` bash
ls
ls /etc
ls -l /etc/
```

以下是无效的，因为你忘了用空白分隔命令的一部分：

``` bash
ls/etc/
ls-l/etc/
```

当你准备好运行一个命令，如 `ls`，按 `Enter/Return` 键。

### 举例

date 命令在屏幕上显示 Linux 系统的日期和时间：

``` bash
date
```

接下来，显示名为 `/etc/hosts` ，和 `/etc/resolv.conf` 的文件内容，运行：

``` bash
cat /etc/hosts
cat /etc/resolv.conf
```

要以长列表格式列出 `/etc/` 目录的内容，请键入：

``` bash
ls -l /etc/
```

让我们用 ls 查看你的主目录中的所有隐藏文件：

``` bash
ls -a $HOME
ls -l -a $HOME
```

## Bash和命令类型

bash shell 能理解以下类型的命令：

- **Aliases（别名）**， 如 `ll` 
- **Keywords（关键字）**， 如 `if`
- **函数**（用户自定义的函数，如 `genpasswd`）
- **Built（内置）**， 如 `pwd`
- **文件**，如 `/bin/date`

`type` 命令可以用来查找命令的类型。

## 命令类型

`type` 命令可以用来找出一个命令是内置的还是外部的二进制文件。

### 找出 ls 是内置的还是外部命令

在 shell 提示符下键入以下命令：

``` bash
type -a ls
```

样例输出：

```
ls is /usr/bin/ls
```

要知道 history 命令是内置的还是外部命令，请输入：

``` bash
type -a history
```

样例输出：

``` bash
history is a shell builtin
```

然而，有些命令是作为内部和外部命令提供的。比如说：

``` bash
type -a true
type -a echo
```

样例输出：

```bash
wm@ubuntu22:~$ type -a true
true is a shell builtin
true is /usr/bin/true
true is /bin/true
wm@ubuntu22:~$ type -a echo
echo is a shell builtin
echo is /usr/bin/echo
echo is /bin/echo
```

### 命令 bash 关键词和内置命令列表

- [JOB_SPEC &](../Commands/JOB SPEC &.md)
- [(( expression ))](https://bash.cyberciti.biz/guide/((_expression_))
- [. filename](../Commands/source%20filename.md)
- [[:]]
- [ arg... ]
- expression
- [alias](../Commands/Alias%E5%91%BD%E4%BB%A4.md)
- [bg](../Commands/Bg.md)
- bind
- builtin
- caller
- case
- command
- compgen
- complete
- continue
- declare
- dirs
- disown
- echo
- enable
- eval
- exec
- exit
- export
- false
- fc
- fg
- for
- getopts
- hash
- help
- history
- if
- jobs
- kill
- let
- local
- logout
- popd
- printf
- pushd
- pwd
- read
- readonly
- return
- select
- set
- shift
- shopt
- source
- suspend
- test
- time
- times
- trap
- true
- type
- typeset
- ulimit
- umask
- unalias
- unset
- until
- variables
- while

