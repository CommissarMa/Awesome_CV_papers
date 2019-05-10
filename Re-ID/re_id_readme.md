# 行人重识别(Re-id)
Re-id 是行人重识别的缩写。  
Re-id的任务是判断两幅图像中的人是否为同一个人。但该任务有许多挑战：
+ 目标被遮挡导致特征丢失。
+ 不同视角及光照条件对识别的影响。
+ 不同的行人穿着相似的衣服。

为了克服这些挑战，研究者们做了许多努力及贡献，主要聚焦于以下方面：
+ 设计了更多适用于人体的特征，如：color&LBP, Gabor, HOG3D, 等等。
+ 选择了多种距离度量方法，如：L2距离, 马氏距离, 等等。
+ 巨量参数的越来越深的网络结构, 或者进行空间映射，使类间距离较小，类间距离较大。

# Paper list and Comprehension
[ACMMM2019 Draft] A Modality Invariant Adversarial Network: Person Re-Identification From Virtuality to Reality [[理解]](./acmmm2019_AMIAN/acmmm2019_AMIAN.md) 

[ACMMM2019 Draft] Dual-alignment Feature Embedding for Cross-modality Person Re-identification [[理解]](./acmmm2019_DFECP/acmmm2019_DFECP.md) 
