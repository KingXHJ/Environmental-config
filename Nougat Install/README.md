# Nougat Install

1. 你需要本地有一个anaconda
2. 在anaconda里创建一个nougat的虚拟环境，python用3.9
3. 去pytorch官网抄一个stable、windows、和你电脑CUDA相同的（命令：nvidia-smi）、pip安装方式的1.13版本的、支持GPU的pytorch（1.13版本在网页中的previous version链接里）
4. 在nougat虚拟环境中把pytorch命令敲进去（不先装CUDA版本的pytorch到时候会报warning：no GPU，using cpu will be slow）
5. 按照facebook的github链接里面第二个pip install的方式安装nougat
6. 去Release中下载模型并放在checkpoint文件夹中

命令示例：

```bash
$ nougat ./input/xxx.pdf -o ./output --batchsize 3 --checkpoint ./checkpoint --recompute
```

```bash
usage: nougat [-h] [--batchsize BATCHSIZE] [--checkpoint CHECKPOINT] [--model MODEL] [--out OUT]
              [--recompute] [--markdown] [--no-skipping] pdf [pdf ...]

positional arguments:
  pdf                   PDF(s) to process.

options:
  -h, --help            show this help message and exit
  --batchsize BATCHSIZE, -b BATCHSIZE
                        Batch size to use.
  --checkpoint CHECKPOINT, -c CHECKPOINT
                        Path to checkpoint directory.
  --model MODEL_TAG, -m MODEL_TAG
                        Model tag to use.
  --out OUT, -o OUT     Output directory.
  --recompute           Recompute already computed PDF, discarding previous predictions.
  --full-precision      Use float32 instead of bfloat16. Can speed up CPU conversion for some setups.
  --no-markdown         Do not add postprocessing step for markdown compatibility.
  --markdown            Add postprocessing step for markdown compatibility (default).
  --no-skipping         Don't apply failure detection heuristic.
  --pages PAGES, -p PAGES
                        Provide page numbers like '1-4,7' for pages 1 through 4 and page 7. Only works for single PDFs.
```

