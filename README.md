# X-EnvironmentConfig
Some environmental configuration experience and note them down

# 目录
- [Config powershell with command autosuggestion](#config-powershell-with-command-autosuggestion)
- [Texlive vscode](#texlive-vscode)
- [VM Fusion Install VM On Apple Silicon](#vm-fusion-install-vm-on-apple-silicon)


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

Find the powershell 7 shortcut and replace the `target` with `"C:\Program Files\PowerShell\7\pwsh.exe" -noe -c "&{  Set-PSReadLineOption -PredictionSource History -ShowToolTips}"  -WorkingDirectory ~` 





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
