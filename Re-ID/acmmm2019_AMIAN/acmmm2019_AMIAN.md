# [ACMMM2019 Draft] A Modality Invariant Adversarial Network: Person Re-Identification From Virtuality to Reality
+ 注意：请使用Chrome浏览器并安装Chrome插件'MathJax Plugin for Github'

## 本文目标
给一张行人的素描图像，然后我们可以判断在其他摄像头拍到的行人是否为该行人。如下图所示：  
![purpose](./purpose.jpg)  

## 提出的方法
![network](./network.jpg)  
在上述图像中，输入A是素描图像，输入B是真实图像。在每个batch中，我们随机挑选了n张素描图像$a^1,a^2,...,a^n$和n张真实图像$b^1,b^2,...,b^n$(其中$a^i$和$b^i$不需要是对应的)。然后我们使用一个生成器G(由一个9层ResNet构成)来将$a^1,a^2,...,a^n$ 和 $b^1,b^2,...,b^n$ 转换成 ${\hat{a^1}},{\hat{a^2}},...,{\hat{a^n}},{\hat{b^1}},{\hat{b^2}},...,{\hat{b^n}}$.  
Through G, we think that ${\hat{a^1}},{\hat{a^2}},...,{\hat{a^n}}$ are in the same space with ${\hat{b^1}},{\hat{b^2}},...,{\hat{b^n}}$ which means they have semantic information in same space and can compare with each other(such as distance metric).   
Then we use two loss to constrain the Back-propagation.  
One is the recognition loss $L_{label}$, which is a cross-entropy function of $c^1,c^2,...,c^n$ with its ground-truth labels.
The other is the adversarial loss $L_{adv}$.  
![equation5](./equation5.jpg) 
$$ {L_{adv}}={-{\frac{1}{n}}}$$

<!--$$L_{adv}=-{\frac 1 n} \sum_{i=1}^n ({m_a^i}\cdot log{D({\hat{a}^i;{\theta}_D})}+{m_b^i}\cdot log(1-D({\hat{b}^i;{\theta}_D})))$$  
And the whole loss is $L_G={\alpha}L_{class}+(-{\beta}L_{adv})$.-->
Finally, we can train this neural network in the manner of end-to-end.

## Two Data Augmentation way
+ Unbalance num of samples in different categories:  
we find the max number $p$ to set the target expanded number, then make up the insufficient sequence of certain pedestrians by copying the original images. 
+ Style Transformation:  
use CycleGAN to transfer the real image to sketch-style-image.

## Proposed New Dataset
Paper use 'MeituXiuXiu' software to construct the dataset.  
![dataset](./dataset.jpg) 
