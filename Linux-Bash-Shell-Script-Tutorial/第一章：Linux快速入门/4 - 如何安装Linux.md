# 如何安装 Linux

你知道什么是 Linux 内核，Linux 发行版以及在哪里下载 Linux 以获得乐趣和利益。接下来让我们看看如何安装 Linux，因为不这样做，你就无法使用它，也无法在 Linux 下学习 Bash 脚本。

## 如何安装 Linux?

请参阅以下部分，其中提供了安装 Linux 的指导和逐步说明。此外，这些是各种 Linux 发行版提供的在你的计算机上安装 Linux 的官方指南：

- [Ubuntu desktop](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview) - 如何在你的笔记本电脑或台式机上安装 Ubuntu 桌面
- [Fedora 35: Installation Guide](https://docs.fedoraproject.org/en-US/fedora/f35/install-guide/) - 在 x86、AMD64 和 Intel 64 架构上安装 Fedora Linux 35 版
- [Red Hat Enterprise Linux 8: Installation Guide](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html-single/performing_a_standard_rhel_installation/index) - 为所有架构安装红帽企业 Linux 版本 8
- [Debian GNU/Linux stable](https://www.debian.org/releases/stable/installmanual) - 安装指南。此外，还包括如何充分利用您的新 Debian 系统的指针和信息。也有一个[快速视频教程/演示](https://youtu.be/FNL8PHxTfkQ)
- [Ubuntu Installation Guide](https://ubuntu.com/server/docs) - 本章提供了一个安装 Ubuntu LTS 服务器版的快速概述。
- [Slackware installation guide](https://www.slackbook.org/) - 在官方网站上有一个[快速帮助](http://www.slackware.com/install/)
- [Linux mint user guide](https://www.linuxmint.com/documentation.php) - Linux Mint 提供了用户指南，指导你完成桌面的安装和使用。
- [OpenSuse installation guide](https://doc.opensuse.org/) - 这个网站承载了 OpenSUSE Leap 和相关项目的文档，包括安装和系统管理主题。
- [Arch Linux installation guide](https://wiki.archlinux.org/index.php/installation_guide) - 本文是一份从使用官方安装镜像启动的实时系统安装 Arch Linux 的指南。

## 创建一个可启动的 USB 盘

要安装 Linux 桌面或服务器，你需要把下载的 ISO CD/DVD 镜像写入 U 盘，以创建安装介质。高级用户可以一直使用 dd 命令来写入 ISO 镜像。但是，建议新用户使用一个叫做 balenaEtcher 的软件。它可以在 Linux、macOS 和 Windows 操作系统上运行。

### 创建你的 USB 盘的其他工具

你可以使用以下软件工具来创建你的 USB 盘。

- [Rufus](https://rufus.ie/en/) 是一个 Windows 工具，帮助格式化和创建可启动的 USB 闪存驱动器，如 USB 钥匙/软盘，记忆棒等。
- 你可以在 Linux 和类 Unix 系统上使用 dd 命令。更多信息请看如何在 Linux 上使用 dd 命令写入/创建 Ubuntu .iso 到可启动的 USB 设备。

### 虚拟化选项

你也可以在虚拟机下安装 Linux 。虚拟机（通常称为 “VM"）是一个虚拟环境，在物理计算机上作为一个虚拟计算机系统运行。最好是使用专门的软件和硬件来运行 VM 。有了虚拟机，你不再需要双启动或格式化磁盘。相反，你可以保留你现有的 Windows 或 macOS 安装，并使用以下称为管理程序的特殊软件来运行 Linux 虚拟机。桌面虚拟化应用程序的一些例子是：

1. [VirtualBox](https://www.virtualbox.org/) (对 Linux/Windows 免费的选择)
2. [QEMU](https://www.qemu.org/) (对 Linux/Windows/Mac 免费的选择)
3. [VMware Workstation Pro](https://www.vmware.com/products/workstation-pro.html) (对 Linux/Mac/Windows 快速的选择)
4. [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install) (仅限 Windows 10/11 桌面或 Windows 服务器 2019)
5. [VMware Fusion](http://www.vmware.com/products/fusion/) (英特尔 Mac 的付费选项)
6. [Parallels Desktop for Mac](https://www.parallels.com/products/desktop/) (英特尔 Mac 和苹果 M1[ARM CPU] 的付费选项)

## 安装 Linux 的通常步骤

1. 下载 Linux ISO CD 或 DVD
2. 将该 CD/DVD 刻录到你的 U 盘或 DVD 上
3. 备份所有现有数据。不要跳过这个步骤
4. 一些 Linux 发行版也允许通过调整现有 Windows 分区的大小进行双启动
5. 然后，重新启动计算机
6. 进入 BIOS 设置，启用从 USB 或 DVD 驱动器启动
7. 插入 USB 笔或 DVD
8. 然后开始从 USB 笔/DVD 启动
9. 屏幕上会弹出 Linux 安装程序
10. 你需要遵循屏幕上的指示