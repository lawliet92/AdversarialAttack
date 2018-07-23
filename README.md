# AdversarialAttack
Sun Yat-sen University Summer Vacation Project

中山大学暑期项目

任务一（60分）： 基础任务，适合无经验者。使用pytorch在minist数据集上训练一个卷积神经网络，要求在测试集上的正确率在90%以上。

提示：

步骤 1：下载minist数据集。 http://yann.lecun.com/exdb/mnist/

步骤 2：在minist数据的训练集上训练一个卷积神经网络。该神经网络要求使用卷积层，并在minist数据测试集上准确率要在90%以上。

提交材料：实验报告一份。

要求 1：实验报告包括标题、实验方法、实验结果、结论、参考文献、附录。

要求 2：以迭代次数iteration或者epoch为横坐标，以loss为纵坐标，绘制训练期间的loss曲线，和测试集上的loss曲线。分析讨论你的模型是否存在过拟合和欠拟合现象，如何改进。分析讨论能否根据该曲线决定何时停止训练，如何决定。

要求 3：统计测试集中神经网络最频繁犯的错误是哪些，如把1误分类为7，并放置相应的例子，和分类概率向量。提出构思如何改进模型使得准确率提高。

参考资料：

一些预训练的pytorch模型 https://github.com/aaron-xichen/pytorch-playground

一个pytorch minist例子 https://github.com/floydhub/mnist

任务二（100分）：高级任务，适合已有经验者。产生minist数据集的对抗样本（adversarial example），并对神经网络进行对抗攻击（adversarial attack）。任务二不限定必须使用pytorch。

对抗样本：由原始样本经过细微变化得到，人眼几乎不能察觉对抗样本和原始样本之间的差异，对抗样本的分类标签在人眼看来也与原始样本一致。但神经网络面对对抗样本会严重出错。

对抗攻击：产生对抗样本，并输入神经网络，使之严重出错。

![alt text](https://github.com/lawliet92/AdversarialAttack/blob/master/advsample.jpeg)

步骤 1：下载minist数据集。 http://yann.lecun.com/exdb/mnist/

步骤 2：取得一个已经在minist数据集上完成训练的神经网络；或者，自行在minist数据的训练集上训练一个神经网络。该神经网络在minist数据测试集上准确率要在90%以上。

步骤 3：确保步骤2中的神经网络能够进行正确的前向计算和后向计算（梯度传播）。可在minist数据的测试集中选择多张图片进行测试，输出每张图片的分类结果即类别概率向量。

步骤 4：使用步骤2中的神经网络，和minist数据集中的测试集图片，来产生对抗样本。基本原理：输入原始样本进入神经网络，使用错误的目标作为监督，然后将梯度回传至输入图片。与训练过程类似，但区别在于不更新神经网络，保持神经网络的参数不变。而把梯度回传到输入图片上，并用该梯度更新输入图片，经过单次或多次更新后，得到对抗样本。

步骤 5：将生成的对抗样本输入到步骤2中的神经网络中进行测试，输出分类结果包括类别概率，并与原始样本的分类结果进行比较。分析对抗样本和原始样本之间的差异，并讨论是否成功地完成了对抗攻击。

提交材料：实验报告一份。

要求 1：实验报告包括标题、实验方法、实验结果、结论、参考文献、附录。

要求 2：实验结果包括罗列图片例子：原始样本图片，对抗样本图片，它们各自的分类概率向量，以及对抗噪声（对抗噪声由对抗样本减去原始样本取绝对值得到，可乘以合适的倍数后转换成RGB图片来可视化，对抗噪声能可视化成一张图片）

要求 3:把对抗噪声看作一个向量，计算它的无穷范数和二范数，作为噪声强度的衡量。探讨随着噪声强度增大，神经网络在对抗样本上的正确率如何变化。

参考资料：

一些预训练的pytorch模型 https://github.com/aaron-xichen/pytorch-playground

一个pytorch minist例子 https://github.com/floydhub/mnist

Intriguing properties of neural networks. https://arxiv.org/abs/1312.6199

Explaining and Harnessing Adversarial Examples. https://arxiv.org/abs/1412.6572

DeepFool: a simple and accurate method to fool deep neural networks https://arxiv.org/abs/1511.04599 https://github.com/LTS4/DeepFool

pytorch 对抗攻击代码 https://github.com/akshaychawla/Adversarial-Examples-in-PyTorch 

pytorch 对抗攻击代码 https://github.com/rwightman/pytorch-nips2017-attack-example 

pytorch 对抗攻击代码 https://github.com/utkuozbulak/pytorch-cnn-adversarial-attacks 
