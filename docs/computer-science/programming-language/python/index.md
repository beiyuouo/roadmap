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
