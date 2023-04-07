# JOB SPEC &

**`＆`** 是 UNIX/Linux 工作控制的一部分。它可以在后台运行命令，并将提示信息反馈给用户，以便你可以运行其他程序。

## 语法

语法如下，在后台运行进程：

```bash
command-name &
/path/to/command2 arg1 arg2 &
/path/to/long/script/namne.sh arg1 &
```

## 例子： 运行后台进程

要使一个名为 ping 的进程成为背景，在 ping 命令行的末尾加上一个 & ，输入：

``` bash
ping baidu.com > /tmp/ping.output &
```

样例输出：

```bash
[1] 140603
```

1 表示工作编号，140603 表示由 Linux 或 UNIX 系统设置的 PID 。

### 列出后台进程

要列出后台进程，请使用 jobs 命令：

``` bash
jobs
```

样例输出：

```
[1]+  Running                 ping baidu.com > /tmp/ping.output &
```

### 关于交互式程序的说明

不要把需要从键盘输入或需要某种用户互动的命令和程序放在这里。下面的例子将无法工作，因为vi文本编辑器需要用户从键盘上进行交互：

``` bash
vi demo.c &
```

passwd 命令更改用户密码，首先会提示用户输入他/她的旧密码，如果有的话。简而言之，passwd 需要从键盘上输入，所以不要把它放到后台：

``` bash
pass
```

