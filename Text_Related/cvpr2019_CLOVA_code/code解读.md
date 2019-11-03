# deep-text-recognition-benchmark
[[代码链接]](https://github.com/clovaai/deep-text-recognition-benchmark)  

## 运行demo.py
1. 将要识别的文本图像放入demo_image
2. run demo.py --Transformation TPS --FeatureExtraction ResNet --SequenceModeling BiLSTM --Prediction Attn --image_folder demo_image/ --saved_model ./pretrain/TPS-ResNet-BiLSTM-Attn-case-sensitive.pth --sensitive  

注：当设置 -- sensitive后，字符类型为94种  0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ!"#$%&'()*+,-./:;<=>?@[\]^_`{|}~