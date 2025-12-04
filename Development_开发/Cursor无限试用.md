---
title: Cursor无限试用
cid: 9
type: post
created: 1742540466
modified: 1742540466
slug: recursor
---

3、提示too many free trial accounts used on this machine，按下面修改硬件id

方案一：手动修改配置文件

定位 storage.json 文件:

Windows: %APPDATA%\Cursor\User\globalStorage

MacOS: ~/Library/Application Support/Cursor

Linux: ~/.config/Cursor/User/globalStorage

修改以下三个参数值:

telemetry.macMachineId

telemetry.machineId

telemetry.devDeviceId

提示：可以修改这些值的后 3-5 位数字

设置文件只读权限:

Windows: 右键文件 → 属性 → 勾选"只读"

MacOS/Linux: 执行 chmod 444 storage.json

重启 Cursor

----zxy: 有更好的办法了
参考：https://github.com/yuaotian/go-cursor-helpChina Users (Recommended)

macOS

```bash
curl -fsSL https://aizaozao.com/accelerate.php/https://raw.githubusercontent.com/yuaotian/go-cursor-help/refs/heads/master/scripts/run/cursor_mac_id_modifier.sh | sudo bash
```

Linux
```bash
curl -fsSL https://aizaozao.com/accelerate.php/https://raw.githubusercontent.com/yuaotian/go-cursor-help/refs/heads/master/scripts/run/cursor_linux_id_modifier.sh | sudo bash
```
Windows
```cmd
irm https://aizaozao.com/accelerate.php/https://raw.githubusercontent.com/yuaotian/go-cursor-help/refs/heads/master/scripts/run/cursor_win_id_modifier.ps1 | iex
```
