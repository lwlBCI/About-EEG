# About-EEG
Try to do some research on EEG signal decoding

主要分为三类：提供脑电信号解码的真实证据(Evidence for decoding EEG signals)、脑电信号解码--情绪识别(EEG Decoding---Emotion Recognition)、脑电信号解码--运动想象(EEG-Decoding---Motor Imagery)

## EEG-Decoding Evidence

[脑电信号解码的真实证据](https://github.com/lwlBCI/EEG-Decoding)

复现了19年neuro science的一篇论文，介绍了跨时域解码/跨任务解码，并介绍了相应的论文

## Classic Deep Learning + EEG Decoding

[EEG-Decoding-Cognition](https://github.com/lwlBCI/EEG-Decoding-Cognition)

是一篇 **脑电信号认知任务量解码+深度学习** 的经典文章，2016年发表于ICLR，尽管其网络结构并不复杂，但几乎是首次结合深度学习方法来进行EEG-Cognition-Decoding的工作。github中有多个复现版本，我个人对其中[tensorflow](https://github.com/YangWangsky/tf_EEGLearn)版本与[pytorch](https://github.com/numediart/EEGLearn-Pytorch)版本进行修改与重运行，并增加了我个人的理解


## EEG Decoding---Emotion Recognition

1.[4D CRNN---DE+PSD](https://github.com/lwlBCI/ER-4D-CRNN)

使用[Deap](http://www.eecs.qmul.ac.uk/mmv/datasets/deap/)和[Seed](https://bcmi.sjtu.edu.cn/~seed/)数据集，复现了两篇脑电情绪识别的代码，综合时域的切片、频域的4个频带提取微分熵DE和功率谱PSD特征、空间域的等距投影等，结合深度学习的CNN和LSTM网络进行了综合的训练和验证，提到的文章是我个人能够发现的、最为清楚的展示深度学习方法在脑电信号情绪识别中应用的，具有典型性/可解释性。

2.TScetion

一种多尺度卷积神经网络，用于从EEG中捕获时间动态和空间不对称。在每个时间/空间层中设计并行多尺度时间/空间核，以丰富学习的时间/频率表示并捕获情感不对称模式。设计了一个高级融合层，以进一步学习EEG的半球/全局表示。

3.ECNN-C

开发了一种简单有效的EEG---Emotion Recognition方法，充分利用情感标签信息，使用一个卷积块来代替标准卷积，大大减少了ECNN模型的计算负担。在实现高识别精度的同时，可以解决数据压缩问题。此外，在模型中引入对比学习来提高情绪样本间的区分能力。该方法可以进一步分离具有不同标签的情感样本，而具有相同标签的情感样品在情感表示空间中彼此靠近。使用对比和交叉熵损失函数来训练ECNN框架。在两个数据集上的实验结果表明，与使用简单的交叉熵损失方法相比，此方法可以达到更高的精度。

4.MTCA-CapsNet

使用的是一种名为MTCA CapsNet网络，胶囊网络多任务学习+通道注意力机制 模型的整体结构由以下四个部分构成：1.通道注意力也就是代码中的ChannelAttention模块，2.一个普通的卷积层nn.Conv2d，3.初级胶囊层，PrimaryCaps模块，4.情绪胶囊层，也就是最后一层DenseCapsule.这个模型的准确率应该是我所想介绍的里面最高的，但是存在的问题是非常复杂且较为新颖，后续看吧，怎么能简单明了的解释

5.ACRNN

卷积递归神经网络，为基于EEG的情绪识别开发了一个数据驱动的ACRNN框架。该框架将通道式注意机制集成到CNN中，以探索空间信息，它可以考虑通道式注意对不同通道的重要性以及CNN对多通道EEG信号的空间信息。此外，ACRNN将扩展自我注意机制集成到RNN中，以探索脑电信号的时间信息，它可以考虑LSTM的不同时间信息和扩展自我注意的每个脑电样本的内在相似性。
