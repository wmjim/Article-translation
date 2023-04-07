# Shell 在 Linux 环境中的作用

Shell 在 Linux 下被用于各种用途。Linux 的用户环境是由以下部分组成的：

- 内核（Kernel）—— Linux 操作系统的核心
- Shell —— 在用户和内核之间提供一个接口
- 终端模拟器 —— xterm 程序是 X 窗口系统的一个终端模拟器。它允许用户输入命令并在屏幕上显示其结果。
- Linux 桌面和 Windows 管理器 - Linux 桌面是各种软件应用的集合。它包括文件管理器、窗口管理器、终端模拟器等等。KDE 和 Gnome 是 Linux 中完整桌面环境的两个例子。


## 注册

当启动级别为 3 时，用户可以在本地登录到控制台，当启动级别为 5 时，用户可以以图形方式登录到控制台（级别的数字可能因发行而不同）。在这两种情况下，你都需要提供用户名和密码。Bash 使用以下初始化和启动文件：

1. `/etc/profile` —— 整个系统的初始化文件，为登录 shells 执行。
2. `/etc/bash.bashrc` —— 整个系统范围内的每个交互式 shell 的启动文件。这是一个非标准的文件，在你的发行版上可能不存在。即使它存在，除非在另一个启动文件中明确地进行，否则它将不会成为源文件。
3. `/etc/bash.logout` —— 全系统的登录 shell 清理文件，在登录 shell 退出时执行。
4. `$HOME/.bash_profile` —— 个人初始化文件，为登录 shell 执行。
5. `$HOME/.bashrc` —— 单独的每个交互式 shell 的启动文件
6. `$HOME/.bash_logout` —— 独立的登录 shell 清理文件，在登录 shell 退出时执行。
7. `$HOME/.inputrc` —— 单独的读行初始化文件。

### Bash 启动脚本

登录时执行的命令脚本，用于设置环境。例如，设置 `JAVA_HOME` 路径。

#### 登录 Shell

登录 shell 是在你登录到系统时启动的第一个 shell。登录 shell 设置的环境会被输出到非登录 shell。当用户登录时，Login shell 会调用下列程序：

- 当用户登录时，`/etc/profile` 首先运行，运行级别 `#3`（级别数字可能因发行版不同而不同）。
  - `/etc/profile.d`

- `$HOME/.bash_profile`、`$HOME/.bash_login` 和 `$HOME/.profile`，当用户登录时按这个顺序运行第二条。`$HOME/.bash_profile` 调用 `$HOME/.bashrc` ，后者调用 `/etc/bashrc（/etc/bash.bashrc）`。

#### 非登录 Shell

- 当一个非登录 shell 的交互式 shell 启动时，bash 会读取并执行 `/etc/bash.bashrc` 或 `/etc/bashrc` 和 `$HOME/.bashrc` 中的命令，如果这些文件存在的话。首先，它调用`$HOME/.bashrc` 。这就调用了 `/etc/bash.bashrc` ，后者调用了 `/etc/profile.d` 。

### Bash 注销脚本

- 当一个登录的 shell 退出时，bash 会读取并执行 `$HOME/.bash_logout` 文件中的命令，如果它存在的话。