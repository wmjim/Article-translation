# Bg

bg 命令是 UNIX/Linux 作业控制的一部分。它用于重新启动一个停止的后台进程。

## 举例

在这个例子中，在前台运行 ping 命令：

``` bash
ping baidu.com
```

### 停止前台进程

要停止名为 ping 的前台进程，按  `[Ctrl-z]`  键。你需要按住 `['Ctrl]` 键并输入 `[z]`。

样例输出：

``` bash
PING baidu.com (110.242.68.66) 56(84) bytes of data.
64 bytes from 110.242.68.66 (110.242.68.66): icmp_seq=1 ttl=50 time=33.4 ms
64 bytes from 110.242.68.66 (110.242.68.66): icmp_seq=2 ttl=50 time=33.4 ms
64 bytes from 110.242.68.66 (110.242.68.66): icmp_seq=3 ttl=50 time=33.3 ms
64 bytes from 110.242.68.66 (110.242.68.66): icmp_seq=4 ttl=50 time=33.4 ms
64 bytes from 110.242.68.66 (110.242.68.66): icmp_seq=5 ttl=50 time=33.6 ms
64 bytes from 110.242.68.66 (110.242.68.66): icmp_seq=6 ttl=50 time=33.4 ms
64 bytes from 110.242.68.66 (110.242.68.66): icmp_seq=7 ttl=50 time=33.6 ms
64 bytes from 110.242.68.66 (110.242.68.66): icmp_seq=8 ttl=50 time=33.4 ms
^Z
[1]+  Stopped                 ping baidu.com
```

### 后台进程列表

要列出后台和停止的进程，请使用 jobs 命令：

样例输出：

``` bash
[1]+  Stopped                 ping baidu.com
```

### 重新启动已停止的进程

要重新启动一个已停止的后台进程（这将重新启动最近停止的进程），请输入：

``` bash
bg
```

或者键入以下内容，重新启动一个已停止的背景进程，该进程的 JOB ID # 10：

``` bash
bg 1
```

