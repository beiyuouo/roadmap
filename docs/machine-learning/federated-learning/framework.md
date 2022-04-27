# Federated Learning 框架

联邦学习发展了这么久了（2016-2021），现在很多大公司也开始做联邦学习相关的内容了，这篇就简单讲一下我接触和了解到的联邦学习框架的介绍吧。因为有些轻量级的框架我阅读了代码，而一些工业/企业级框架我只了解了一下架构，说的也不一定全对，大家辩证看待就好。

每个框架都有其优点和缺点，如果时间在计划内，会做一个对比图。

其实从这也能看出来，已经有不少公司和企业认识到了 FL 的前景，也投入的不少研究。

> 以下排名不分先后

## FATE - Webank

Code: [https://github.com/FederatedAI/FATE](https://github.com/FederatedAI/FATE)

Docs: [https://fate.readthedocs.io/en/latest/?badge=latest](https://fate.readthedocs.io/en/latest/?badge=latest)

Architecture:

![](https://fate.readthedocs.io/en/latest/_images/fateflow_arch.png)

优点：

- 面向企业的分布式部署，框架功能完善，容错性强
- 支持多种编程语言开发
- 工业级框架，版本更新迭代快
- 社区活跃，热度高
- 支持的算法多

缺点：

- 难配置，不适合做 Research
- 上手难
- 不支持 Windows

## TensorFlow-Federated - Google

Code: [https://github.com/tensorflow/federated](https://github.com/tensorflow/federated)

Docs: [https://www.tensorflow.org/federated](https://www.tensorflow.org/federated)

优点：

- API 提供全面
- 文档丰富
- 社区良好
- 很多工作已经基于 TFF 了

## Pysyft - OpenMind

Code: [https://github.com/OpenMined/PySyft](https://github.com/OpenMined/PySyft)

Docs: [https://www.openmined.org/](https://www.openmined.org/)

优点：

- 灵活的 api
- 支持隐私计算
  缺点
- 现在很多 api 都在实验开发阶段，可能会遇到各种各样的问题
- 用的人和知道的人不算太多

## 9nFL - JD

Code: [https://github.com/jd-9n/9nfl](https://github.com/jd-9n/9nfl)

> 不知道是不是还活着...

## FedLearner - ByteDance

Code: [https://github.com/bytedance/fedlearner](https://github.com/bytedance/fedlearner)

> 看 Star 数量感觉活跃度一般，文档也不是很全

## Clara - NVIDIA

Docs: [https://docs.nvidia.com/clara/](https://docs.nvidia.com/clara/)

![](https://docs.nvidia.com/clara/deploy/_images/clara_overview_components.png)

> 有 Release，但是好像未开源？

## Paddle-FL - Baidu

Code: [https://github.com/paddlepaddle/PaddleFL](https://github.com/paddlepaddle/PaddleFL)

Docs: [https://paddlefl.readthedocs.io/en/latest/](https://paddlefl.readthedocs.io/en/latest/)

![](https://github.com/PaddlePaddle/PaddleFL/raw/master/images/FL-framework.png)

优点：

- 面向 PaddlePaddle，结构简单

缺点

- 迭代慢 ~~，似乎已经弃坑？~~ 好久没看最近好像又开始更新了
- 目前不支持 PaddlePaddle 最新版本

## AngelFL - Tencent

![](https://pic3.zhimg.com/80/v2-115868ed04d426ed15cff701fadecfca_720w.jpg)

> 未开源，不做评价了，想了解可以看官方的说明[https://zhuanlan.zhihu.com/p/112983993](https://zhuanlan.zhihu.com/p/112983993), 还有官网[https://data.qq.com/powerfl/](https://data.qq.com/powerfl/)

## flower - Adap

Code: [https://github.com/adap/flower](https://github.com/adap/flower)

Docs: [https://flower.dev/docs/](https://flower.dev/docs/)

优点：

- 支持很多框架(TF, PyTorch, scikit-learn, MXNet)
- 结构简单，易上手

缺点：

- 扩展性较差

## iBond-flex - tongdun

Code: [https://github.com/tongdun/iBond-flex](https://github.com/tongdun/iBond-flex)

> 面向 Research 的，主要是隐私计算那一块

## plato - Huawei

Code: [https://github.com/TL-System/plato](https://github.com/TL-System/plato)

> 最近出来的新框架，文档还不完善

## IBMFL - IBM

Code: [https://github.com/IBM/federated-learning-lib](https://github.com/IBM/federated-learning-lib)

Docs: [http://ibmfl-api-docs.mybluemix.net/index.html](http://ibmfl-api-docs.mybluemix.net/index.html)

![](https://raw.githubusercontent.com/IBM/federated-learning-lib/main/docs/floverview.png)

## FedML

Code: [https://github.com/FedML-AI/FedML](https://github.com/FedML-AI/FedML)

Docs: [https://fedml.ai/](https://fedml.ai/)

优点：

- 轻量级
- 支持多种 IoT 设备等，适合边缘计算
- 支持 wandb

缺点：

- Code 存在错误，社区迭代较慢

## OpenFed

Code: [https://github.com/FederalLab/OpenFed](https://github.com/FederalLab/OpenFed)

Docs: [https://openfed.readthedocs.io/README.html](https://openfed.readthedocs.io/README.html)

> 现在加上我，一共 5 个 Star，只能说新的不能在新了...

优点

- 基于 MMLab(什么含金量不用多说了吧)

## FedLab

![](https://fedlab.readthedocs.io/en/master/_images/fedlab-overview-dark.svg)

Code: [https://github.com/SMILELab-FL/FedLab](https://github.com/SMILELab-FL/FedLab)

Docs: [https://fedlab.readthedocs.io/en/master/index.html](https://fedlab.readthedocs.io/en/master/index.html)

优点：

- 轻量级
- 新框架，支持异步逻辑

缺点：

- 对策略支持不够灵活

## OpenFL - Intel

Code: [https://github.com/intel/openfl](https://github.com/intel/openfl)

Docs: [https://openfl.readthedocs.io/en/latest/index.html](https://openfl.readthedocs.io/en/latest/index.html)

![](https://openfl.readthedocs.io/en/latest/_images/static_diagram.svg)

> 也是刚开始发展，仍在开发中，目前实现的算法不多

优点：

- 支持多种后端框架（Keras、TF、PyTorch）

# Summary

[comment]: <> (
| Framework | Sync | HFL | VFL | Hetero | Async | Encrypt | Cross Platform |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| **FATE** | :white_check_mark: | :white_check_mark: | :white_check_mark:| :white_check_mark: | :x: | :white_check_mark: | :x: |
)

# Reference

[1] [https://zhuanlan.zhihu.com/p/387101962](https://zhuanlan.zhihu.com/p/387101962)
