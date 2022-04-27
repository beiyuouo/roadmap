# PyTorch

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
