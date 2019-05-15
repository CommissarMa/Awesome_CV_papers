# [CVPR2019] Context-Aware Crowd Counting

## 本文目标
利用多尺度的感受域来提高群体计数的精度。

## 提出的方法
![network](./network.png)
上图是作者提出的Context-Aware Network。我个人理解：这个网络是在CSRNet基础上结合多尺度接受域的思想改进而成的。  
具体来说，网络的输入是3通道的彩色图像，经过VGG16的前10层组成的front-end network，得到feature map，然后经过多尺度接受域部分得到weighted feature maps，然后在channel上连接feature map和weighted feature maps组成一个新的feature输入到back-end decoder，最后得到密度图。然后用SGD训练即可，end-to-end。  
多尺度接受域部分参考上图中的下半张图，对feature maps，我们采用{1，2，3，6}这4种尺度进行平均池化，然后做一个1*1Conv并双线性插值回原来maps的尺寸，记这个新的maps为$S_j$，然后用$S_j$减去feature maps得到contrast feature $C_j$，然后对4个尺度上的$C_j$进行加权平均即为weighted feature maps。  
下图为front-end network和back-end network的具体参数设置。
![structure](./structure.png)  
注意：feature map和weighted feature maps进行通道上的连接，则通道的维度是512+512=1024。因此back-end第一层的input channel=1024。

## 实验效果
在ShanghaiTech A数据集上取得了62.3的结果，很强！  
据作者说：在Titan xp上训练两天能够收敛，进行了数据增强(水平flip)。在ShanghaiTech B上可以加大batch_size，一天即可收敛。
![result](./result.png)