# X-EnvironmentConfig
Some environmental configuration experience and note them down

# 目录
- [配置zsh & oh-my-zsh](#配置zsh--oh-my-zsh)
- [Config powershell with command autosuggestion](#config-powershell-with-command-autosuggestion)
- [Config Visual Studio Code With Props](#config-visual-studio-code-with-props)
- [Texlive vscode](#texlive-vscode)
- [VM Fusion Install VM On Apple Silicon](#vm-fusion-install-vm-on-apple-silicon)

## 配置zsh & oh-my-zsh

zsh和oh my zsh的配置方法请见[zsh deploy](./Zsh-oh-my-zsh-Deployment/zsh_deploy.sh)

## Config powershell with command autosuggestion

1. First [download powershell 7](https://zhuanlan.zhihu.com/p/401439255)

```powershell
Get-Host | Select-Object Version

winget search powershell

# If have more than one record, then use the version ID
winget install Microsoft.PowerShell

# Finally change the default terminal in terminal settings
```

2. Config the autosuggestion autostart

Find the powershell 7 shortcut(快捷方式), right click `property` and replace the `target` with `"C:\Program Files\PowerShell\7\pwsh.exe" -noe -c "&{  Set-PSReadLineOption -PredictionSource History -ShowToolTips}"  -WorkingDirectory ~` 


## Config Visual Studio Code With Props
1. OpenCV
    1. 系统环境变量
        - (你的磁盘名):\Opencv460\opencv\build\x64\vc15\bin
    1. VC++目录 -> 包含目录
    1. VC++目录 -> 库目录
    1. 链接器 -> 附加依赖项
1. OpenXLSX
    1. VC++目录 -> 包含目录
    1. VC++目录 -> 库目录
    1. 链接器 -> 附加依赖项

1. PCL
    1. 系统环境变量
        - (你的磁盘名):\PCL\PCL 1.12.1\bin
        - (你的磁盘名):\PCL\PCL 1.12.1\3rdParty\OpenNI2\Tools
        - (你的磁盘名):\PCL\PCL 1.12.1\3rdParty\FLANN\bin
        - (你的磁盘名):\PCL\PCL 1.12.1\3rdParty\Qhull\bin
        - (你的磁盘名):\PCL\PCL 1.12.1\3rdParty\VTK\bin




## Texlive vscode

### 下载Texlive
```
Tsinghua Open Source Mirror
```

### 安装扩展
```
LaTex Workshop
LaTex language support
```

### Settings.json
配置settings.json文件


## VM Fusion Install VM On Apple Silicon
An important instruction

> The PDF gives all details for users to install virtual machines on apple silicon!
