# Python

## Quick Start

别的不说，安装 Python 环境必装 conda，作为环境管理器简直不要太方便，用着也很顺手

1. 按照[官方文档](https://conda.io/projects/conda/en/latest/user-guide/install/index.html)中 Regular installation 选择自己的操作系统，然后安装即可。Linux 会让你下一个 sh，Windows 就直接是 installer 了。
2. 创建环境 `conda create -n [env-name] python=[version]`
3. 切换环境 `conda activate [env-name]`

如果不想命令行左边一直有 `base`，可以默认关闭 `base` 环境，然后在 `conda` 命令行中执行 `conda config --set auto_activate_base false`

如果有需要可以添加一下清华源

```sh
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/
conda config --set show_channel_urls yes
conda config --get channels
```

## PyTorch

官网<a href="https://pytorch.org/get-started/locally/">https://pytorch.org/get-started/locally/</a>

目前长期支持版只有一个，`1.8.2`，可以通过下面的方式安装

```sh
conda install pytorch torchvision torchaudio cudatoolkit=10.2 -c pytorch-lts
# or
pip install torch==1.8.2+cu102 torchvision==0.9.2+cu102 torchaudio==0.8.2 -f https://download.pytorch.org/whl/lts/1.8/torch_lts.html
```

如果最新版就是

```sh
conda install pytorch torchvision torchaudio cudatoolkit=10.2 -c pytorch
# or
pip install torch torchvision torchaudio
```
