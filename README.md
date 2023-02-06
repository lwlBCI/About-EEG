# About-EEG
Try to do some research on EEG signal decoding

主要分为三类：提供脑电信号解码的真实证据(Evidence for decoding EEG signals)、脑电信号解码--情绪识别(EEG Decoding---Emotion Recognition)、脑电信号解码--运动想象(EEG-Decoding---Motor Imagery)

## EEG-Decoding Evidence

[脑电信号解码的真实证据](https://github.com/lwlBCI/EEG-Decoding)

复现了19年neuro science的一篇论文，介绍了跨时域解码/跨任务解码，并提到了对应的论文

## Classic Deep Learning + EEG Decoding

[EEG-Decoding-Cognition](https://github.com/lwlBCI/EEG-Decoding-Cognition)

是一篇 脑电信号认知任务量解码+深度学习 的经典文章，2016年发表于ICLR，尽管其网络结构并不复杂，但几乎是首次结合深度学习方法来进行EEG-Cognition-Decoding的工作。github中有多个复现版本，我个人对其中[tensorflow](https://github.com/YangWangsky/tf_EEGLearn)版本与[pytorch](https://github.com/numediart/EEGLearn-Pytorch)版本进行修改与重运行，并增加了我个人的理解


## EEG Decoding---Emotion Recognition

[4D CRNN---DE+PSD](https://github.com/lwlBCI/ER-4D-CRNN)

使用[Deap](http://www.eecs.qmul.ac.uk/mmv/datasets/deap/)和[Seed](https://bcmi.sjtu.edu.cn/~seed/)数据集，复现了两篇脑电情绪识别的代码，综合时域的切片、频域的4个频带提取微分熵DE和功率谱PSD特征、空间域的等距投影等，结合深度学习的CNN和LSTM网络进行了综合的训练和验证，提到的文章是我个人能够发现的、最为清楚的展示深度学习方法在脑电信号情绪识别中应用的，具有典型性/可解释性。
