---
title: Windows 安装MiniConda(配置环境PowerShell问题自定义虚拟环境路径)
cid: 5
type: post
created: 1741186676
modified: 1741186676
slug: 5
---

# 一、Minicanda安装
打开浏览器,跳转到[MiniConda官网](https://docs.anaconda.com/miniconda/),向下滑动找到并点击Miniconda3 Windows 64-bit
# 二、安装MiniConda
无脑下一步,安装完毕
# 三、添加环境变量
> path\to\your\miniconda
path\to\your\miniconda\Library\bin
path\to\your\miniconda\Scripts 

# 四、PowerShell问题
- 打开PowerShell终端
- 键入指令`conda init powershell`，初始化conda
- 键入指令`Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`修改PowerShell限制策略
- 重启PowerShell，检查conda activate是否生效
# 五、设置虚拟环境安装路径
在C:\Users\用户名中找到 .condarc 文件，选中右键，在记事本中编辑打开，将下面的文本复制进去

```
envs_dirs:
  - D:\soft\Miniconda\envs
  
pkgs_dirs:
  - D:\soft\Miniconda\pkgs
```
然后给虚拟环境路径添加权限
