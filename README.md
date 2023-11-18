# X-EnvironmentConfig
Some environmental configuration experience and note them down

# 目录
- [配置zsh & oh-my-zsh](#配置zsh--oh-my-zsh)
- [Config powershell with command autosuggestion](#config-powershell-with-command-autosuggestion)
- [Config Visual Studio Code With Props](#config-visual-studio-code-with-props)
- [Texlive vscode](#texlive-vscode)
    - [下载Texlive](#下载texlive)
    - [安装扩展](#安装扩展)
    - [Settings.json](#settingsjson)
- [VM Fusion Install VM On Apple Silicon](#vm-fusion-install-vm-on-apple-silicon)
- [VScode markdown print pdf without formular efficient](#vscode-markdown-print-pdf-without-formular-efficient)
- [pip 使用国内源](#pip-使用国内源)
    - [临时使用](#临时使用)
    - [永久使用](#永久使用)

## 配置zsh & oh-my-zsh

zsh和oh my zsh的配置方法请见[zsh deploy](./Zsh-oh-my-zsh-Deployment/zsh_deploy.sh)

But Windows has [another way](./Zsh-oh-my-zsh-Deployment/zsh_deploy_windows.md)


[返回目录](#目录)


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


[返回目录](#目录)


## Config Visual Studio Code With Props
1. OpenCV
    1. 系统环境变量
        - (你的磁盘名):\Opencv460\opencv\build\x64\vc15\bin
    1. VC++目录 -> 包含目录
    1. VC++目录 -> 库目录
    1. 链接器 -> 输入 -> 附加依赖项
1. OpenXLSX
    1. VC++目录 -> 包含目录
    1. VC++目录 -> 库目录
    1. 链接器 -> 输入 -> 附加依赖项
    1. 更改：C/C++ -> 语言 -> C++语言标准 -> ISO C++ 17 标准（/std:c++17）

1. PCL
    1. 系统环境变量
        - (你的磁盘名):\PCL\PCL 1.12.1\bin
        - (你的磁盘名):\PCL\PCL 1.12.1\3rdParty\OpenNI2\Tools
        - (你的磁盘名):\PCL\PCL 1.12.1\3rdParty\FLANN\bin
        - (你的磁盘名):\PCL\PCL 1.12.1\3rdParty\Qhull\bin
        - (你的磁盘名):\PCL\PCL 1.12.1\3rdParty\VTK\bin


[返回目录](#目录)


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
配置[settings.json文件](./Texlive%20vscode/settings.json)


[返回目录](#目录)


## VM Fusion Install VM On Apple Silicon
An important instruction

> The PDF gives all details for users to install virtual machines on apple silicon!


[返回目录](#目录)


## VScode markdown print pdf without formular efficient
1. Install ```Markdown PDF``` in VScode
1. Find the file in path ```C://Users/<username>/.vscode/extensions/yzane.markdown-pdf-1.4.1/template/template.html```
1. Add 
    ```
    <script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
    <script type="text/x-mathjax-config"> MathJax.Hub.Config({ tex2jax: {inlineMath: [['$', '$']]}, messageStyle: "none" });</script>
    ```
    before ```</html>```, after ```</body>```


[返回目录](#目录)


## pip 使用国内源

```
清华大学：https://pypi.tuna.tsinghua.edu.cn/simple
阿里云：http://mirrors.aliyun.com/pypi/simple/
豆瓣：http://pypi.douban.com/simple/
```

### 临时使用

```sh
pip install -i http://pypi.douban.com/simple/ numpy
pip install -i http://pypi.douban.com/simple/--trusted-host pypi.douban.com  #此参数“--trusted-host”表示信任，如果上一个提示不受信任，就使用这个
```

### 永久使用

1. Linux平台安装方式：
    - 创建pip.conf文件
    1. 首先创建```.pip```目录：
        ```sh
        mkdir ~/.pip
        cd ~/.pip
        ```

    1. 在 .pip目录下创建一个 pip.conf 文件并编辑:
        ```sh
        sudo vim pip.conf
        ```
    1. 写入以下内容：
        ```sh
        [global] 
        index-url = https://pypi.tuna.tsinghua.edu.cn/simple
        [install]
        trusted-host = https://pypi.tuna.tsinghua.edu.cn
        # trusted-host 此参数是为了避免麻烦，否则使用的时候可能会提示不受信任
        ```
    1. 然后保存退出即可。


[返回目录](#目录)
