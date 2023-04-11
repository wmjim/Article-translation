# shell 中的变量

你可以使用变量来**==存储数据==**和**==配置选项==**。有两种类型的变量，如下所示：

## 系统变量

由 Linux bash shell 自己创建和维护。这种类型的变量（除了 auto_resume 和 histchars 之外）是用大写字母定义的。你可以通过修改系统变量来配置 shell 的各个方面，比如 PS1、PATH、LANG、HISTSIZE 和 DISPLAY 等。

### 查看所有系统变量

要查看所有的系统变量，在控制台/终端键入以下命令：

``` bash
set

# OR

env

# OR

printenv
```

set 命令的输出样本：

``` bash
BASH=/bin/bash
BASH_ARGC=()
BASH_ARGV=()
BASH_LINENO=()
BASH_SOURCE=()
BASH_VERSINFO=([0]="3" [1]="2" [2]="39" [3]="1" [4]="release" [5]="i486-pc-linux-gnu")
BASH_VERSION='3.2.39(1)-release'
COLORTERM=gnome-terminal
COLUMNS=158
DBUS_SESSION_BUS_ADDRESS=unix:abstract=/tmp/dbus-FSGj0JzI4V,guid=7f59a3dd0813f52d6296ee404a9a68e1
DESKTOP_SESSION=gnome
DIRSTACK=()
DISPLAY=:0.0
EUID=1000
GDMSESSION=gnome
GDM_LANG=en_IN
GDM_XSERVER_LOCATION=local
GNOME_DESKTOP_SESSION_ID=this-is-deprecated
GPG_AGENT_INFO=/tmp/gpg-X7NqIv/S.gpg-agent:7340:1
GROUPS=()
GTK_RC_FILES=/etc/gtk/gtkrc:/home/vivek/.gtkrc-1.2-gnome2
HISTFILE=/home/vivek/.bash_history
HISTFILESIZE=500
HISTSIZE=500
HOME=/home/vivek
HOSTNAME=vivek-desktop
HOSTTYPE=i486
IFS=$' \t\n'
LANG=en_IN
LINES=57
LOGNAME=vivek
MACHTYPE=i486-pc-linux-gnu
MAILCHECK=60
OLDPWD=/home/vivek
OPTERR=1
OPTIND=1
ORBIT_SOCKETDIR=/tmp/orbit-vivek
OSTYPE=linux-gnu
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games
PIPESTATUS=([0]="0")
PPID=7542
PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
PS2='> '
PS4='+ '
PWD=/tmp
SESSION_MANAGER=local/vivek-desktop:/tmp/.ICE-unix/7194
SHELL=/bin/bash
SHELLOPTS=braceexpand:emacs:hashall:histexpand:history:interactive-comments:monitor
SHLVL=1
SSH_AGENT_PID=7339
SSH_AUTH_SOCK=/tmp/ssh-IoFXYh7194/agent.7194
TERM=xterm
UID=1000
USER=vivek
USERNAME=vivek
WINDOWID=18874428
WINDOWPATH=7
XAUTHORITY=/home/vivek/.Xauthority
XDG_DATA_DIRS=/usr/local/share/:/usr/share/:/usr/share/gdm/
XDG_SESSION_COOKIE=186611583e30fed08439ca0047067c9d-1251633372.846960-528440704
_=set
command_not_found_handle () 
{ 
    if [ -x /usr/lib/command-not-found ]; then
        /usr/bin/python /usr/lib/command-not-found -- $1;
        return $?;
    else
        return 127;
    fi
}
mp3 () 
{ 
    local o=$IFS;
    IFS=$(echo -en "\n\b");
    /usr/bin/beep-media-player "$(cat  $@)" & IFS=o
}
genpasswd () 
{ 
    local l=$1;
    [ "$l" == "" ] && l=16;
    tr -dc A-Za-z0-9_ < /dev/urandom | head -c ${l} | xargs
}
xrpm () 
{ 
    [ "$1" != "" ] && ( rpm2cpio "$1" | cpio -idmv )
}
```

### 常用的 shell 变量

以下变量由 shell 设置：

| 系统变量     | 目的                                                         | 查看变量值类型                          | 输出                                                         |
| ------------ | ------------------------------------------------------------ | --------------------------------------- | ------------------------------------------------------------ |
| BASH_VERSION | 保存这个 bash 实例的版本。                                   | echo $BASH_VERSION                      | 5.2.2(1)-release                                             |
| HOSTNAME     | 您的计算机的名称。                                           | echo $HOSTNAME                          | ubuntu22                                                     |
| CDPATH       | cd命令的搜索路径。                                           | echo $CDPATH                            |                                                              |
| HISTFILE     | 保存命令历史的文件名。                                       | echo $HISTFILE                          | /home/wm/.bash_history                                       |
| HISTFILESIZE | 历史文件中包含的最大行数。                                   | echo $HISTFILESIZE                      | 2000                                                         |
| HISTSIZE     | 命令历史中要记住的命令数量。默认值是500。                    | echo $HISTSIZE                          | 1000                                                         |
| HOME         | 当前用户的home目录。                                         | echo $HOME                              | /home/wm                                                     |
| IFS          | 内部字段分隔符，用于扩展后的字段分割，以及用读取内置命令将行分割成字。默认值是 `<space><tab><newline>`。 | echo $IFS                               |                                                              |
| LANG         | 用于确定任何没有特别选择以 `LC_` 开头的变量的类别的地域类别。 | echo $LANG                              | en_US.UTF-8                                                  |
| PATH         | 命令的搜索路径。它是一个用冒号分隔的目录列表，shell在其中寻找命令。 | echo $PATH                              | /home/wm/.local/bin<br />:/home/wm/bin:/home/wm/.cargo/bin<br />:/home/wm/.loacl/bin:/usr/local/sbin<br />:/usr/local/bin:/usr/sbin:/usr/bin:/sbin<br />:/bin:/usr/games:/usr/local/games:/snap/bin |
| PS1          | 你的提示设置。                                               | echo $PS1                               | \[\e]0;\u@\h: \w\a\]${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ |
| TMOUT        | read 内置命令的默认超时。在交互式shell 中，该值也被解释为发出命令后等待输入的秒数。如果没有提供输入，它将注销用户。 | echo $TMOUT                             |                                                              |
| TERM         | 你的登录终端类型。                                           | echo $TERM <br />export TERM=vt100      | xterm-256color                                               |
| SHELL        | 设置登录 shell 的路径。                                      | echo $SHELL                             | /bin/bash                                                    |
| DISPLAY      | 设置 X 显示名称                                              | echo $DISPLAY <br />export DISPLAY=:0.1 |                                                              |
| EDITOR       | 设置默认文本编辑器的名称。                                   | export EDITOR=/usr/bin/vim              |                                                              |

- 注意你可以将上述变量（导出命令）添加到位于你账户主目录下的初始化文件中，如 `~/.bash_profile`。

### 如何显示一个变量的值？

使用 echo 命令来显示变量值。要显示程序的搜索路径，请键入：

``` bash
echo "$PATH"
```

要显示你的提示设置，请键入：

``` bash
echo "$PS1"
```

所有的变量名都必须以 `$` 符号为前缀，整个结构应该用引号括起来。试试下面的例子，在不使用 `$` 前缀的情况下显示一个变量的值：

``` bash
echo "HOME"
```

用 echo $HOME 来显示一个变量的值：

``` bash
echo "$HOME"
```

你必须在变量名称前使用 $ 来打印变量的内容，变量名称也可以用大括号括起来：

``` bash
echo "${HOME}"
```

当变量名后面紧跟着字符时，用大括号把变量名括起来很有用：

``` bash
echo "${HOME}work"
```

#### 向 printf 问好

printf 命令就像 echo 命令一样，在不同版本的 UNIX 操作系统下都可以使用。如果可移植性是你关注的主要问题，那么使用 printf 是一个好主意。其语法如下：

``` bash
printf "$VARIABLE_NAME\n"
printf "String %s" $VARIABLE_NAME
printf "Signed Decimal Number %d" $VARIABLE_NAME
printf "Floating Point Number %f" $VARIABLE_NAME
```

要显示程序搜索路径，请键入：

``` bash
printf "$PATH\n"

# OR

printf "The path is set to %s\n" $PATH
```

样例输出：

``` bash
The path is set to /home/vivek/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games
```

## 用户自定义的变量

由用户创建和维护。这种类型的变量定义可以使用任何有效的变量名称，但避免全部大写的名称是很好的做法，因为很多都是由 shell 使用的。