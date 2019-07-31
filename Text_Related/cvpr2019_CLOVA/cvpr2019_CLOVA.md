# What is wrong with scene text recognition model comparisons? dataset and model analysis  
[[论文链接]](https://arxiv.org/abs/1904.01906) 
[[代码]](https://github.com/clovaai/deep-text-recognition-benchmark)  

## 摘要
近年来提出了很多新的场景文本识别(STR)方法，然而虽然这些方法都声称自己很有效，但由于训练数据集与评估数据集的不一致，因此缺乏一个公平的比较。本文为解决这一难题提出了三点贡献：
1. 检查训练集与测试集的不一致程度以及所带来的精度上的差异。
2. 提出了一个四阶段的STR框架，大部分现有的STR模型都能使用该框架。因此能很好地评估这些方法。
3. 我们分析了每个模块对最终准确率、速度和内存需求的贡献程度。