# 将Aria2注册为Apple silicon芯片的Mac的启动服务
## 介绍:
如果你正在使用搭载 Apple Silicon (M1/M2) 的Mac，并且希望通过 Homebrew 来启动和停止 Aria2 服务, 本教程将指导你如何创建必要的文件让 Aria2 完美的工作在你的设备上

本仓库提供的文件已针对 macOS Sonoma beta5 以上版本进行优化，解决了 Aria2 在 Sonoma 下无法运行的问题[aria2 doesn't work in Sonoma #2083](https://github.com/aria2/aria2/issues/2083)

### 步骤1: Install Aria2 using Homebrew
确保你已经在你的Mac上安装了 Aria2 and Homebrew. 如果没有，你可以参考以下网站的介绍:

- Homebrew: https://brew.sh/
- Aria2: 安装通过 `brew install aria2`

### 步骤2: 创建 Aria2 服务文件
想要为 Aria2 启用 `brew services` 命令, 你需要在 Aria2 的安装目录下创建一个 plist 服务文件 ，具体如下:
1. 下载本仓库中的 [homebrew.mxcl.aria2.plist](https://github.com/412999826/aria2-macOS/raw/main/homebrew.mxcl.aria2.plist)

2. 在 Mac 上打开访达,定位到 Aria2 在 Homebrew 的安装目录 (本文以 Aria2 的 1.36.0_2 版本为例，根据安装的版本不同，目录位置会有细微不同):

   同时按下Shift-Command-G，前往 `/opt/homebrew/Cellar/aria2/1.36.0_2`目录
3. 将刚才下载的 `homebrew.mxcl.aria2.plist` 文件拷贝到此目录

### 步骤3: 启动/停止 Aria2 服务
- 运行并注册 Aria2 服务:

```
brew services start aria2
```

- 停止并删除 Aria2 服务:

```
brew services stop aria2
```

#### 其余设置
Aria2默认的配置文件在当前用户的aria2文件夹下，同时按下Shift-Command-G，前往`~/.aria2`目录后，编辑`aria2.conf`即可


