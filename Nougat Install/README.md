# Nougat Install

1. 你需要本地有一个anaconda
2. 在anaconda里创建一个nougat的虚拟环境，python用3.9
3. 去pytorch官网抄一个stable、windows、和你电脑CUDA相同的（命令：nvidia-smi）、pip安装方式的1.13版本的、支持GPU的pytorch（1.13版本在网页中的previous version链接里）
4. 在nougat虚拟环境中把pytorch命令敲进去（不先装CUDA版本的pytorch到时候会报warning：no GPU，using cpu will be slow）
5. 按照facebook的github链接里面第二个pip install的方式安装nougat