### Text_Classification-TFIDF+GBDT


## 目标：

* 使用提供的20Newsgroups文本训练数据集建立一个模型，该模型可以预测测试集上的文本数据的分类标签。并给出在各个子分类上的准确率（precision）、召回率（recall）和 F1 得分（f1-score）。

## 介绍：
这是一个有监督的分类机器学习任务：给定一组包含分类标签的数据，我们希望从文本中提取相应的特征，并训练一个可以学习将特征映射到目标标签的模型。

* 有监督问题： 我们可以知道数据的特征和目标，我们的目标是训练可以学习两者之间映射关系的模型。
* 分类问题： 文本标签是一个字符类型变量，可以编码成有限数量的离散变量。
* 数据集： 20newsgroups数据集是用于文本分类、文本挖据和信息检索研究的国际标准数据集之一。数据集收集了大约20000左右的新闻组文档，均匀分为20个不同主题的新闻组集合。
* 算法： [GBDT算法原理](./20Newsgroups/GBDT)

为了测试模型的学习效果，我们在一个从未参与训练的测试集上进行指标评估。

## 流程：
* 加载并检查数据。
* 针对每个文档，统计词频，并去除停用词和出现次数出现频率超过一定阈值的词。
* 根据词频向量得出每个文档的TF-IDF特征向量。
* 得到TF-IDF特征向量和类别标签作为输入，使用XGBoost进行多分类任务训练。
* 测试集上预测并评估性能，给出各分类上的准确率（precision）、召回率（recall）和 F1 得分（f1-score）。


