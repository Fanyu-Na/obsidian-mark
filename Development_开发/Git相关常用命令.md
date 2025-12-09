---
title: git 设置用户名邮箱
cid: 8
type: post
created: 1742030820
modified: 1742030944
slug: git-config
---

在Git中，设置用户名和邮箱是非常重要的，因为它能帮助你在提交代码时正确地标识自己。你可以通过以下步骤来设置Git的用户名和邮箱：

### 1. 配置全局用户名和邮箱
如果你想要为你的所有Git仓库设置相同的用户名和邮箱，你可以使用git config --global命令。打开你的终端或命令提示符，然后输入以下命令：

```bash
git config --global user.name "Ekzykes"
git config --global user.email "atlaseuan@163.com"
```

将"你的用户名"和"你的邮箱@example.com"替换为你的实际用户名和邮箱。

### 2. 配置特定仓库的用户名和邮箱
如果你只想为特定的Git仓库设置用户名和邮箱，而不是全局设置，你可以在仓库目录下使用以下命令：

```bash
git config user.name "Ekzykes"
git config user.email "atlaseuan@163.com"
```

同样地，将"你的用户名"和"你的邮箱@example.com"替换为你的实际信息。


### 3. 检查配置
为了确认你的设置是否成功，你可以使用以下命令来查看全局或特定仓库的配置：

查看全局配置：


```bash
git config --global --list
```

查看特定仓库的配置：


```bash
git config --local --list
```

或者在当前仓库目录下运行git config --list。

这些命令将列出所有已配置的Git设置，包括用户名和邮箱。你可以通过这些信息来验证你的设置是否正确。

注意事项
确保你使用的邮箱是你希望与Git提交关联的邮箱。如果你使用的是工作邮箱，请确保该邮箱可以接收来自GitHub等服务的邮件（例如，验证邮件）。

如果在提交代码时遇到问题（如提交信息中显示错误的用户名或邮箱），通常是因为Git的配置没有正确设置或者使用了错误的仓库路径。确保你在正确的仓库目录下执行了git config命令。

### 4.⚙️ 设置 `core.fileMode`

Git 默认会跟踪文件的执行权限位（即 `+x` 或 `-x` 的变化），这是通过配置变量 `core.fileMode`（默认值为 `true`）控制的。

要让 Git **忽略**文件模式的更改，请执行以下命令：

#### 1. 针对当前仓库设置

如果您只想在**当前 Git 仓库**中忽略文件权限的更改，请在仓库的根目录下运行：

Bash

```
git config core.fileMode false
```

这会在该仓库的 `.git/config` 文件中写入设置。

#### 2. 全局设置

如果您想让 **所有本地 Git 仓库** 默认都忽略文件权限的更改，请使用 `--global` 标志：

Bash

```
git config --global core.fileMode false
```

这会在您的用户主目录下的全局 Git 配置文件（通常是 `~/.gitconfig`）中写入设置。

#### 📌 注意事项

- **Git 仅跟踪执行权限（Executable Bit）：** Git 只会跟踪文件的 **执行权限** (`100755` vs `100644`) 的变化，不会跟踪文件的读写权限（`rw-` 部分）的变化。
    
- 设置 `core.fileMode false` 后，如果文件内容没有变化，即使文件模式（执行权限）发生了变化，`git status` 也**不会**将其识别为待提交的更改。
    
- 在不同的操作系统（特别是跨 Windows 和类 Unix 系统协作时），这个设置特别有用，因为这些系统处理文件权限的方式可能不同。
    
---

#### 🔍 检查当前设置

要检查 `core.fileMode` 当前的值，可以使用以下命令：

```bash
git config core.fileMode
```

如果输出是 `false`，则说明设置已生效。如果没有任何输出，则表示使用的是默认值 `true`（或者可以尝试 `git config -l | grep filemode`）。