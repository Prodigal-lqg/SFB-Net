
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
1.We crop the original images and their corresponding annotations into 256×256 patches to standardize the input size for training.

2.Patches with less than 30% parcel coverage are discarded to reduce class imbalance, and the remaining data are split into 5,499 training samples, 1,376 validation samples, and 1,208 testing samples to ensure a balanced dataset for model development and evaluation.

3.We apply multiple data augmentation techniques, including flipping, mirroring, Gaussian noise, contrast adjustment, scaling, and mix-up, to enhance sample diversity and improve model generalization..


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
from CSGMNet import Field

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
