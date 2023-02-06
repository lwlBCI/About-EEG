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

## EEG-Decoding---Motor Imagery

1.[EEG-MI-ATCNet](https://github.com/lwlBCI/EEG-MI-ATCNet)

使用的数据集为[BCI Competition IV-2a](http://www.bbci.de/competition/iv/#dataset2a)，ATCNet结构主要由三个模块构成：卷积块，注意力(AT)块，时间卷积块，并且包含一个滑动卷积结构。相较于经典的EEGNet、DeepConvNet等网络效果更好，可解释性更强。该模型借鉴于TCNet也就是前几年非常火爆的TCN结构在EEG-MI任务上的应用进行改进，加入了注意力机制与滑动卷积结构增加了数据量。

另外，关于这篇文章的复现代码中包含EEGNet、DeepConvNet、ShallowConvNet等多种经典EEG-MI网络模型可供读者比较使用，各种模型代码均可运行。

2.MMCNN

多分支多尺度卷积，提出的MMCNN由5个并行EEG初始网络(EIN)组成，包括15种卷积核大小.该模型在不进行任何预处理(包括滤波)的情况下有效地解码原始EEG信号，具有很大的实际应用前景。其次，多分支多尺度卷积结构可以成功地解决基于并行处理的MI分类的受试者差异和时间差异问题。并且此模型可以基于更少的EEG信道(具体地，论文中作者只用了三个通道)获得更高的分类结果。

3.FBCNet

提出了一种用于MI分类的新型滤波器组卷积网络（FBCNet）。FBCNet采用多视图数据表示，然后进行空间滤波，以提取光谱空间分辨特征。即使在有限的训练数据可用时，这种多级方法也能够有效地训练网络。更重要的是，在FBCNet中，我们提出了一种新的方差层，可以有效地聚集EEG时域信息并减少参数。

4.FBMSNet

对FBCNet中进行了翻版改进，利用的是FBCNet中提供的训练逻辑、数据结构(多滤波器机制)、SCB模块、方差层结构等等。加入新的东西：一个是在SCB模块之前加入了混合卷积Mixconv，一个是加入了中心损失，与交叉熵损失一起联合监督，最后便是在训练的过程中能够把分类层前的特征层提取出来，然后利用T-SNE画出在288个数据在进入分类层之前的大致分布情况。
