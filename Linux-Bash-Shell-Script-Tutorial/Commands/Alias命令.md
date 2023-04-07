# Alias 命令

要定义或显示 bash shell 的别名，请使用 alias 命令。

## 怎样查看别名

键入以下命令：

``` bash
alias
```

样例输出：

``` bash
alias alert='notify-send --urgency=low -i "$([ $? = 0 ] && echo terminal || echo error)" "$(history|tail -n1|sed -e '\''s/^\s*[0-9]\+\s*//;s/[;&|]\s*alert$//'\'')"'
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'
alias grep='grep --color=auto'
alias l='ls -CF'
alias la='ls -A'
alias ll='ls -alF'
alias ls='ls --color=auto'
alias update='sudo -- sh -c "apt update && apt upgrade"'
```

## 如何定义别名

语法是

``` bash
alias name=value
```

要定义一个名为vnstat的别名：

``` bash
alias vnstat='vnstat -i eth0'
```

## 怎样使用别名

只需输入你的别名即可：

``` bash
vnstat
```

样例输出：

``` bash
Database updated: Thu Nov 16 06:19:15 2017

   eth0 since 07/16/17

          rx:  125.80 TiB      tx:  24.72 TiB      total:  150.51 TiB

   monthly
                     rx      |     tx      |    total    |   avg. rate
     ------------------------+-------------+-------------+---------------
       Oct '17    464.51 GiB |   85.78 GiB |  550.30 GiB |    1.72 Mbit/s
       Nov '17    213.76 GiB |   41.87 GiB |  255.63 GiB |    1.63 Mbit/s
     ------------------------+-------------+-------------+---------------
     estimated    420.14 GiB |   82.30 GiB |  502.44 GiB |

   daily
                     rx      |     tx      |    total    |   avg. rate
     ------------------------+-------------+-------------+---------------
     yesterday     15.87 GiB |    3.00 GiB |   18.87 GiB |    1.83 Mbit/s
         today      2.96 GiB |  528.68 MiB |    3.47 GiB |    1.28 Mbit/s
     ------------------------+-------------+-------------+---------------
     estimated     11.23 GiB |    1.96 GiB |   13.19 GiB |
```

## 如何从定义的别名列表中删除每个别名

语法是：

``` bash
unalias name
```

要删除一个名为 vnstat 的别名：

``` bash
unalias vnstat
```

要删除所有的别名定义，请在 alias 命令中加上 `-a` 选项：

``` bash
alias -a
```

## 另见

- [创建和使用别名](https://bash.cyberciti.biz/guide/Create_and_use_aliases)
- [Linux / Unix / MacOS的30个方便的Bash Shell别名](https://www.cyberciti.biz/tips/bash-aliases-mac-centos-linux-unix.html)
- [Bash Shell在运行命令时忽略了别名和函数](https://www.cyberciti.biz/faq/ignore-shell-aliases-functions-when-running-command/)
