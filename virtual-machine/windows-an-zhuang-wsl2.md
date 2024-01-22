# Windows 安装 wsl2

### **必要条件**

要在 Windows 10 上安装 WSL 2，您需要以下东西：

* Windows 10 2020年5月(2004) 版, Windows 10 2019年5月(1903) 版，或者 Windows 10 2019年11月(1909) 版
* 一台支持 Hyper-V 虚拟化的计算机

Windows 10 2020年5月更新已于 2020年5月发布（显然），但并非每个设备都能立即升级。要查看您的计算机上是否有 Windows 10 2020年5月更新，请转至“设置” > “更新和安全性” > “Windows 更新”。在 8 月， [微软将 WSL 2 向后移植](https://link.zhihu.com/?target=https://devblogs.microsoft.com/commandline/wsl-2-support-is-coming-to-windows-10-versions-1903-and-1909/) 到 Windows 10 的较早版本。版本号为 1903 或 1909 的任何人也可以安装WSL 2 —— 但必须首先安装 [Windows 更新 KB4566116](https://link.zhihu.com/?target=https://support.microsoft.com/zh-cn/help/4566116/windows-10-update-kb4566116)。高级（和心急）的 Windows 用户可以强制安装 Windows 10 2020年5月更新，但请记住，如果按照这种方法操作，您可能会遭遇缺失驱动程序、GUI 故障或其他硬件故障。从技术上来讲，您可以在 Windows 10 build 18917 或更高版本的“内部”版本上安装 WSL 2。我不太熟悉“内部”版本系统是如何工作的，所以请注意，本文的其余部分都基于在稳定版的 Windows 上使用该功能。为了运行 WSL 2，您的计算机还需要支持 Hyper-V 虚拟化。您可以 [检查您的计算机确认对 Hyper-V 的支持](https://link.zhihu.com/?target=https://www.zdnet.com/article/windows-10-tip-find-out-if-your-pc-can-run-hyper-v/) 。如果您不能同时满足这两个必要条件，则无法安装或启用 WSL 2——但可以使用 WSL 1。在 Windows 10 上安装 WSL 2 的过程如下：

1. 启用 WSL 2
2. 启用“虚拟机平台”
3. 设置 WSL 2 为默认值
4. 安装 Linux 发行版

我将使用 PowerShell 应用程序依次介绍每个步骤，您需要以管理员身份运行此应用程序。您可以在 Windows “开始” 菜单中找到 PowerShell。注意：也可以使用 GUI 安装 WSL 1，但使用命令行安装的速度要快得多，而且由于 WSL 是 CLI 工具，这也比较讲得通！

### **第 1 步，启用 WSL**

不管您想要使用哪个版本的 WSL，都首先需要启用它。为此，请**以管理员身份打开 PowerShell 工具并运行以下命令**。小心不要在命令中输入错误或遗漏任何字符：

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

如果只想使用 WSL 1，您可以跳到第 4 步。

### **第 2 步，启用“虚拟机平台”**

WSL 2 需要启用 Windows 10 的 “虚拟机平台” 特性。它独立于 Hyper-V，并提供了一些在 Linux 的 Windows 子系统新版本中可用的更有趣的平台集成。要在 Windows 10（2004）上启用虚拟机平台，请以管理员身份打开 PowerShell 并运行：

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

要在 Windows 10（1903，1909）上启用虚拟机平台，请以管理员身份打开 PowerShell 并运行：

```powershell
Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform -NoRestart
```

为了确保所有相关部件都整齐到位，您应该在**此时重启系统**，否则可能会发现事情没按预期进行。

### **第 3 步，设置 WSL 2 为默认值**

以管理员身份打开 PowerShell，然后运行以下命令以将 WSL 2 设置为 WSL 的默认版本：

```powershell
wsl --set-default-version 2
```

如果需要，您可以（随时）将发行版配置为以 WSL 1 模式运行。

### **第 4 步，安装一个 Linux 发行版**

有了 WSL 和必要的虚拟化技术，接下来您要做的就是从 Microsoft Store 中选择并安装 Linux 发行版。有几种不同的发行版可供选择，包括 OpenSUSE、Pengwin、Fedora Remix 和 Alpine Linux。但是我个人推荐（自然地）Ubuntu 20.04 LTS（尽管也有 18.04 LTS 和 16.04 LTS 可用）。

1. 要在 Windows 10 上安装 Ubuntu，请打开 Microsoft Store 应用，搜索 “Ubuntu 20.04”，然后单击“获取”按钮
2. 当您在 Microsoft Store 中时，我强烈建议您**也安装开源的 Windows Terminal 应用程序**。该工具旨在为您提供最佳的 WSL 体验：

### **第 5 步，使用 WSL 2**

当您安装 Ubuntu（或其他 Linux 发行版）时，快捷方式已添加到 Windows “开始”菜单中。使用它可以“打开” Ubuntu（或您选择的任何发行版）。第一次运行发行版时，速度似乎有点慢。这是预料之中的；发行版必须解压缩其所有内容——只是不要中断这个过程。还将提示您设置用于发行版的用户名和密码。尝试挑选一些您不会忘记的字符。

***

## **注意事项**

1. WslRegisterDistribution failed with error: 0x800701bc

造成该问题的原因是WSL版本由原来的WSL1升级到WSL2后，内核没有升级，前往微软WSL官网下载安装适用于 x64 计算机的最新 WSL2 Linux 内核更新包即可。下载链接：&#x20;

{% embed url="https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi" %}
下载链接
{% endembed %}

