
# SFBNet: Semantic–Frequency Boundary Network

## 🌱 Introduction
SFBNet (Semantic–Frequency Boundary Network) is a multi-task deep learning framework for agricultural parcel delineation from high-resolution remote sensing imagery.
It introduces two complementary modules:
1. **Complementary Semantic Attention (CSA)**  
   Enhances cross-scale semantic consistency.
   Stabilizes region–boundary alignment through spatial priors and channel interactions.  

2. **Frequency-domain Boundary Enhancement Module (FBEM)**  
   Incorporates frequency-domain modeling to refine boundary sharpness.
   Produces continuous and accurate boundaries even under low-contrast or complex textures.

---
## Data Preprocessing
This study utilizes remote sensing datasets from both the Netherlands and Denmark.
Netherlands dataset covers typical intensive agricultural areas, where parcels are generally large and heterogeneous, while also including some small irregular fields. After cropping the images into 256×256 patches and discarding samples with less than 30% parcel coverage, the dataset consists of 4,970 training samples, 1,243 validation samples, and 1,041 testing samples

Denmark dataset is characterized by fragmented and irregular parcels distributed in terrain-influenced heterogeneous landscapes. Such parcels often exhibit weak or discontinuous boundaries, posing greater challenges for accurate delineation. Similar to the Netherlands dataset, the images and annotations were cropped into 256×256 patches, and samples with less than 30% parcel coverage were discarded. According to the defined partition strategy, the red-marked regions (A, B, D, F, G) were assigned to the training set, the green-marked regions (C, E) to the validation set, and the remaining regions to the test set. In total, the Denmark dataset contains 5,535 training samples, 1,383 validation samples, and 1,297 testing samples
<p align="center">
<img width="639" height="800" alt="75cc7391fbc579158f0e673e2fda7b6c" src="https://github.com/user-attachments/assets/897532a7-8786-45c5-a46a-81226f5befd6" />
</p>


To further enhance model generalization, multiple data augmentation techniques were applied during training, including random flipping, mirroring, Gaussian noise, contrast adjustment, scaling, and mix-up. These augmentations effectively increased sample diversity and alleviated the negative impact of parcel fragmentation and blurred boundaries.
## ⚙️ Installation
Clone this repository:
```bash
git clone https://github.com/Prodigal-lqg/SFB-Net.git
cd SFB-Net

```
## 🚀 Usage
Run the following example to test the model:

```python
import torch
from SFB-Net import Field

model = Field()
x = torch.randn(1, 3, 256, 256)

outputs = model(x)
mask, edge, distance = outputs
```
## 🚀 Usage
Netherlands: large heterogeneous parcels.

Denmark: small irregular parcels with weak boundaries.
## 📜 Citation

If you find this work useful, please cite our paper:

```bibtex
@inproceedings{jia2025sfbnet,
  title={SFBNet: A Semantic–Frequency Boundary Network for Agricultural Parcel Delineation},
  author={Jia, Liruizhi and Li, Ye and Kong, Bo and Liu, Chao and Liu, Yuan and Liu, Shengquan},
  booktitle={ICASSP},
  year={2025}
}

```
##  Acknowledgement

We are very grateful for these excellent works BsiNet, and HBGNet, which have provided the basis for our framework.

```bibtex
@article{zhao2025hbgnet,
  author       = {Zhao, Hang and Wu, Bingfang and Zhang, Miao and Long, Jiang and Tian, Fuyou and Xie, Yan and Zeng, Hongwei and Zheng, Zhaoju and Ma, Zonghan and Wang, Mingxing and others},
  title        = {A large-scale VHR parcel dataset and a novel hierarchical semantic boundary-guided network for agricultural parcel delineation},
  journal      = {ISPRS Journal of Photogrammetry and Remote Sensing},
  volume       = {221},
  pages        = {1--19},
  year         = {2025},
  doi          = {10.1016/j.isprsjprs.2025.01.034}
}
@article{LONG2022102871,
title = {Delineation of agricultural fields using multi-task BsiNet from high-resolution satellite images},
journal = {International Journal of Applied Earth Observation and Geoinformation},
volume = {112},
pages = {102871},
year = {2022},
issn = {1569-8432},
doi = {https://doi.org/10.1016/j.jag.2022.102871},

author = {Jiang Long and Mengmeng Li and Xiaoqin Wang and Alfred Stein},
}

```
