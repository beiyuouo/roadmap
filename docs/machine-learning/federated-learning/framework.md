# Federated Learning 框架

联邦学习发展了这么久了（2016-2022），现在很多大公司也开始做联邦学习相关的内容了，这篇就简单讲一下我接触和了解到的联邦学习框架的介绍吧。因为有些轻量级的框架我阅读了代码，而一些工业/企业级框架我只了解了一下架构，说的也不一定全对，大家辩证看待就好。

每个框架都有其优点和缺点，如果时间在计划内，会做一个对比图。

其实从这也能看出来，已经有不少公司和企业认识到了 FL 的前景，也投入的不少研究。

> 以下排名不分先后

## Quick View

这一节主要是为了快速让读者知道联邦学习框架有哪些，以及它们背后的公司、设计逻辑和优缺点。

### FATE - Webank

Code: [https://github.com/FederatedAI/FATE](https://github.com/FederatedAI/FATE)

Docs: [https://fate.readthedocs.io/en/latest/?badge=latest](https://fate.readthedocs.io/en/latest/?badge=latest)

Architecture:

![](https://fate.readthedocs.io/en/latest/_images/fateflow_arch.png)

优点：

缺点：

### TensorFlow-Federated - Google

Code: [https://github.com/tensorflow/federated](https://github.com/tensorflow/federated)

Docs: [https://www.tensorflow.org/federated](https://www.tensorflow.org/federated)

优点：

缺点：

### Pysyft - OpenMind

Code: [https://github.com/OpenMined/PySyft](https://github.com/OpenMined/PySyft)

Docs: [https://www.openmined.org/](https://www.openmined.org/)

优点：

缺点：

### 9nFL - JD

Code: [https://github.com/jd-9n/9nfl](https://github.com/jd-9n/9nfl)
Docs: Unknown

> 最后一次更新时 2020.12，不知道现在是不是还活着...

### FedLearner - ByteDance

Code: [https://github.com/bytedance/fedlearner](https://github.com/bytedance/fedlearner)

### Clara - NVIDIA

Docs: [https://docs.nvidia.com/clara/](https://docs.nvidia.com/clara/)

![](https://docs.nvidia.com/clara/deploy/_images/clara_overview_components.png)

> 有 Release，但是好像未开源？

### Paddle-FL - Baidu

Code: [https://github.com/paddlepaddle/PaddleFL](https://github.com/paddlepaddle/PaddleFL)

Docs: [https://paddlefl.readthedocs.io/en/latest/](https://paddlefl.readthedocs.io/en/latest/)

![](https://github.com/PaddlePaddle/PaddleFL/raw/master/images/FL-framework.png)

优点：

缺点

### AngelFL - Tencent

Code: Unknown

Docs: Unknown

![](https://pic3.zhimg.com/80/v2-115868ed04d426ed15cff701fadecfca_720w.jpg)

> 未开源，不做评价了，想了解可以看官方的说明[https://zhuanlan.zhihu.com/p/112983993](https://zhuanlan.zhihu.com/p/112983993), 还有官网[https://data.qq.com/powerfl/](https://data.qq.com/powerfl/)

### flower - Adap

Code: [https://github.com/adap/flower](https://github.com/adap/flower)

Docs: [https://flower.dev/docs/](https://flower.dev/docs/)

优点：

缺点：

### iBond-flex - tongdun

Code: [https://github.com/tongdun/iBond-flex](https://github.com/tongdun/iBond-flex)

Docs: Unknown

### plato - Huawei

Code: [https://github.com/TL-System/plato](https://github.com/TL-System/plato)

Docs: Unknown

### IBMFL - IBM

Code: [https://github.com/IBM/federated-learning-lib](https://github.com/IBM/federated-learning-lib)

Docs: [http://ibmfl-api-docs.mybluemix.net/index.html](http://ibmfl-api-docs.mybluemix.net/index.html)

Architecture:

![](https://raw.githubusercontent.com/IBM/federated-learning-lib/main/docs/floverview.png)

### FedML

Code: [https://github.com/FedML-AI/FedML](https://github.com/FedML-AI/FedML)

Docs: [https://doc.fedml.ai/](https://doc.fedml.ai/)

Architecture:

- 利用 MPI/NPCC 进行底层进程驱动，当然也提供了 SingleThread 的版本
- 实现了多种通讯协议的支持

### OpenFed

Code: [https://github.com/FederalLab/OpenFed](https://github.com/FederalLab/OpenFed)

Docs: [https://openfed.readthedocs.io/README.html](https://openfed.readthedocs.io/README.html)

> 现在加上我，一共 5 个 Star，只能说新的不能在新了...

优点：

### FedLab

Code: [https://github.com/SMILELab-FL/FedLab](https://github.com/SMILELab-FL/FedLab)

Docs: [https://fedlab.readthedocs.io/en/master/index.html](https://fedlab.readthedocs.io/en/master/index.html)

Architecture:

![](https://fedlab.readthedocs.io/en/master/_images/fedlab-overview-dark.svg)

优点：

缺点：

### OpenFL - Intel

Code: [https://github.com/intel/openfl](https://github.com/intel/openfl)

Docs: [https://openfl.readthedocs.io/en/latest/index.html](https://openfl.readthedocs.io/en/latest/index.html)

Architecture:

![](https://openfl.readthedocs.io/en/latest/_images/static_diagram.svg)

优点：

### FederatedScope - alibaba

Code: [https://github.com/alibaba/FederatedScope](https://github.com/alibaba/FederatedScope)

Docs: [https://federatedscope.io/](https://federatedscope.io/)

Paper: [https://arxiv.org/abs/2204.05011.pdf](https://arxiv.org/abs/2204.05011.pdf)

Architecture:

> 今日[2022.5.5]刚开源的项目

- 利用 yacs 配置文件
- gRPC 通信协议
- 提供了 Dockerfile
- 以事件驱动的消息队列，异步处理
- 可以自定义的计算资源，通过 register 来注册
- Auto-tuning
- 提供多种隐私保护机制，同态加密、差分隐私，以及攻击方法
- 提供了 attack 方法

## Framework Comparison

在这一节，会用几个不同的维度来对比这些框架，还未完成，仅占位。

## Summary

|     Framework      |        Sync        |        HFL         |        VFL         |       Hetero       | Async |      Encrypt       | Cross Platform |
| :----------------: | :----------------: | :----------------: | :----------------: | :----------------: | :---: | :----------------: | :------------: |
| **FederatedScope** | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: |  :x:  | :white_check_mark: |      :x:       |

## Reference

[1] [https://zhuanlan.zhihu.com/p/387101962](https://zhuanlan.zhihu.com/p/387101962)
