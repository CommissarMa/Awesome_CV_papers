# Re-id
Re-id is the abbreviation of Person Re-Indentification.
Re-id judges whether the person in two still images are the same person. But there are many challenges:
+ Occlusion which makes some feature loss.
+ Different views and illumination under different cameras.
+ Different person with similar clothes.

To overcome these challenges, much effort has been paid which mainly focus on the following aspects:
+ design more suitable feature for human body such as color&LBP, Gabor, HOG3D, etc.
+ choose proper distance metric such as L2 Norm, mahalanobis distance, etc.
+ deeper and deeper nerual networks with more parameters, or space mapping with low intra-distance and high inter-distance.

# Paper list and Comprehension
[ACMMM2019 Draft] A Modality Invariant Adversarial Network: Person Re-Identification From Virtuality to Reality [[comprehension]](./acmmm2019_AMIAN/acmmm2019_AMIAN.md) 
