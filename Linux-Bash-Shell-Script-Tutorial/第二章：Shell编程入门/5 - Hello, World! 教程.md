# Hello, World! 教程

要创建一个 shell 脚本：

1. 使用一个文本编辑器，如 vi。在文件中写入所需的 Linux 命令和逻辑。
2. 保存并关闭该文件（退出 vi）。
3. 使该脚本可执行。
4. 然后，你当然应该测试这个脚本，一旦对输出结果满意，就把它移到生产环境中去。
5. Bash 中最简单的程序是由一行告诉计算机一个命令组成的。启动你喜欢的文本编辑器（比如vi）：

``` bash
vi hello.sh
```

## 基本的 Vi 命令

- 打开一个文件

``` bash
vi filename
```

- 进入编辑模式
  
``` bash
按下 ESC，并输入 I
```

- 进入命令模式

``` bash
按下 ESC
```

- 保存一个文件

``` bash
按下 ESC，并输入 :w fileName
```

- 保存一个文件并退出

``` bash
按下 ESC，并输入 :wq

# OR

按下 ESC，并输入 :x
```

- 要跳到某一行：

``` bash
按ESC键，输入 :行号
```

- 要搜索一个字符串

``` bash
按ESC键, 并输入 /wordToSearch
```

- 退出 vi

``` bash
按ESC键并输入 :q
```

将以下内容保存到一个名为 hello.sh 的文件中：

``` bash
#!/bin/bash
echo "Hello, World!" 
echo "Knowledge is power."
```

保存并关闭该文件。你可以按以下方式运行该脚本：

``` bash
./hello.sh
```

样例输出:

``` bash
bash: ./hello.sh: Permission denied
```

## 保存和运行你的脚本

./hello.sh 命令在屏幕上显示了一条错误信息。因为你没有为你的脚本 hello.sh 设置执行权限，所以它不会运行脚本。要执行这个程序，请输入以下命令：

``` bash
chmod +x hello.sh
./hello.sh
```

样例输出:

``` bash
Hello, World!
Knowledge is power.
```

## 另见

- [chmod command](https://bash.cyberciti.biz/guide/Chmod_command)
- [vi command](https://bash.cyberciti.biz/guide/Vi_command)