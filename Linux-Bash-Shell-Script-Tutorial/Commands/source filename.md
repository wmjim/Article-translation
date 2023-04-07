# . filename

`. filename` （或 `source filename`）将在当前 shell 中执行名为 filename 的命令。

## 语法

在当前 shell 中读取并执行 `/home/wm/bin/email-alert.lib.sh` 的命令：

``` bash
. /home/wm/bin/email-alert.lib.sh
# OR
source "/home/wm/bin/email-alert.lib.sh"
```

## 退出状态

它将返回 `/home/wm/bin/email-alert.lib.sh` 中最后执行的命令的状态；如果 `/home/wm/bin/email-alert.lib.sh` 无法被读取，则会失败。你可以用 `$?` 变量来验证：

``` bash
echo $?
printf "%d\n" $?
```

更多信息见[退出状态页面](./%E5%91%BD%E4%BB%A4%E7%9A%84%E9%80%80%E5%87%BA%E7%8A%B6%E6%80%81.md)。

## 举例

创建一个名为 `cli_app.sh` 的文件，如下所示：

``` bash
push_to_mobile(){
	local t="${1:cli-app}"
	local m="$2"
	[[ "$m" != "" ]] && curl -s \
	  --form-string "token=MY_TOKEN_HERE" \
	  --form-string "user=MY_USER_NAME_HERE" \
	  --form-string "title=$t" \
	  --form-string "message=$m" \
	  https://api.pushover.net/1/messages.json
}
```

现在我们可以在我们的 shell 脚本中使用 cli_app.sh ，如下所示：

``` bash
[ -f "/home/wm/bin/cli_app.sh" ] && . "/home/wm/bin/cli_app.sh"

notify(){
	if declare -F push_to_mobile >/dev/null
	then
		push_to_mobile "$0:${FUNCNAME[0]}->$1()" "RDS IP changed from '${ld_rds_ip:-NEW_MISSING_RULE}' to '$rds_current_ip' on $HOSTNAME LS-AWS {$instance_ip}" >/dev/null
	fi
}
```

## 得到帮助

使用 man 命令或 help 命令，如下所示：

``` bash
man bash
help .
help source
```

## 另见

- [如何从 Linux CLI 推送/发送消息到 iOS 和 Android](https://www.cyberciti.biz/mobile-devices/android/how-to-push-send-message-to-ios-and-android-from-linux-cli/)
- [如何在电池电量耗尽时关闭 FreeBSD 笔记本电脑](https://bash.cyberciti.biz/monitoring/shell-script-to-shutdown-freebsd-laptop-when-low-on-battery-power/)