# PointCloud-Registration-Tracing

Inspired by [awesome-point-cloud-registration](https://github.com/XuyangBai/awesome-point-cloud-registration) and [awesome-computer-vision](https://github.com/jbhuang0604/awesome-computer-vision).

This list focuses on the rigid registration between point clouds and tracks progress in point cloud registration research.

## Table of Contents
- 1.[Overview](#overview)
- 2.[Coarse Registration (Global Registration)](#coarse-registration)
    - 2.1 [Feature Matching Based](#feature-matching-based)
        - 2.1.1 [Feature Description](#feature-description)
        - 2.1.2 [Keypoint Detection](#keypoint-detection)
        - 2.1.3 [Outlier Rejection](#outlier-rejection)
        - 2.1.4 [Graph Algorithms](#graph-algorithms)
    - 2.2 [End-to-End](#end-to-end)
    - 2.3 [Randomized](#randomized)
    - 2.4 [Probablistic](#probabilistic)
- 3.[Fine Registration (Local Registration)](#fine-registration)
    - 3.1 [Learning-based](#learning-based)
    - 3.2 [Traditional](#traditional)
- 4.[Datasets](#datasets)
- 5.[Tools](#tools)

### 1.Overview
- [Deep learning based point cloud registration: an overview](https://www.sciencedirect.com/science/article/pii/S2096579620300383) 【VRIH, 2020】
- [A comprehensive survey on point cloud registration](https://arxiv.org/pdf/2103.02690) 【arXiv, 2021】
- [Transformers in 3D Point Clouds: A Survey](https://arxiv.org/pdf/2205.07417) 【arXiv, 2022】
- [A review of non-rigid transformations and learning-based 3D point cloud registration methods](https://www.sciencedirect.com/science/article/pii/S0924271622003380)【ISPRS, 2023】


### 2.Coarse Registration

#### 2.1 Feature Matching Based
##### 2.1.1 Feature Description
###### (1) Point-based Strategy
- [PPFNet: Global Context Aware Local Features for Robust 3D Point Matching](http://arxiv.org/pdf/1802.02669)【CVPR, 2018】
- [PPF-FoldNet: Unsupervised Learning of Rotation Invariant 3D Local Descriptors](https://arxiv.org/abs/1808.10322)【ECCV, 2018】【[code](https://github.com/XuyangBai/PPF-FoldNet)】
- [3DFeat-Net: Weakly Supervised Local 3D Features for Point Cloud Registration](https://arxiv.org/pdf/1807.09413.pdf)【ECCV, 2018】【[code](https://github.com/yewzijian/3DFeatNet)】
- [D3Feat: Joint Learning of Dense Detection and Description of 3D Local Features](https://arxiv.org/abs/2003.03164) 【CVPR, 2020】【[code](https://github.com/XuyangBai/D3Feat)】

###### (2) Voxel-based Strategy
- [3DMatch: Learning Local Geometric Descriptors from RGB-D Reconstructions](http://arxiv.org/pdf/1603.08182)【CVPR, 2017】 【[code](https://github.com/andyzeng/3dmatch-toolbox)】
- [The Perfect Match: 3D Point Cloud Matching with Smoothed Densities](https://arxiv.org/abs/1811.06879)【CVPR, 2019] 【[code](https://github.com/zgojcic/3DSmoothNet)】
- [FCGF: Fully Convolutional Geometric Features](https://openaccess.thecvf.com/content_ICCV_2019/papers/Choy_Fully_Convolutional_Geometric_Features_ICCV_2019_paper.pdf) 【ICCV, 2019】【[code](https://github.com/chrischoy/FCGF)】

###### (3) Point-Voxel Strategy

###### (4) Line-based Strategy
- [SuperLine3D: Self-supervised Line Segmentation and Description for LiDAR Point Cloud](https://arxiv.org/pdf/2208.01925)【ECCV, 2022】【[code](https://github.com/zxrzju/SuperLine3D)】

###### (5) Transformer-based Strategy
- [Full Transformer Framework for Robust Point Cloud Registration with Deep Information Interaction](https://arxiv.org/pdf/2112.09385)【arXiv, 2021】
- [Geometric Transformer for Fast and Robust Point Cloud Registration](https://openaccess.thecvf.com/content/CVPR2022/papers/Qin_Geometric_Transformer_for_Fast_and_Robust_Point_Cloud_Registration_CVPR_2022_paper.pdf)【CVPR, 2022】【[code](https://github.com/qinzheng93/GeoTransformer)】

###### (6) Other Strategy
- [SpinNet: Learning a General Surface Descriptor for 3D Point Cloud Registration](https://arxiv.org/abs/2011.12149)【CVPR, 2021】【[code](https://github.com/QingyongHu/SpinNet)】
- [You Only Hypothesize Once: Point Cloud Registration with Rotation-equivariant Descriptors](https://arxiv.org/abs/2109.00182)【ICCV, 2021】【[code](https://github.com/HpWang-whu/YOHO)】

##### 2.1.2 Keypoint Detection
- [USIP: Unsupervised Stable Interest Point Detection From 3D Point Clouds](https://openaccess.thecvf.com/content_ICCV_2019/papers/Li_USIP_Unsupervised_Stable_Interest_Point_Detection_From_3D_Point_Clouds_ICCV_2019_paper.pdf)【ICCV, 2019】【[code](https://github.com/lijx10/USIP)】
- [Point cloud saliency detection by local and global feature fusion](https://ieeexplore.ieee.org/stampPDF/getPDF.jsp?tp=&arnumber=8726371&ref=)【T-IP, 2019】
- [D3Feat: Joint Learning of Dense Detection and Description of 3D Local Features](https://arxiv.org/abs/2003.03164) 【CVPR, 2020】【[code](https://github.com/XuyangBai/D3Feat)】
- [3D3L: Deep learned 3D keypoint detection and description for lidars](https://arxiv.org/pdf/2103.13808)【ICRA, 2021】【[code](https://github.com/ethz-asl/3d3l)】
- [UKPGAN: A General Self-Supervised Keypoint Detector](https://openaccess.thecvf.com/content/CVPR2022/papers/You_UKPGAN_A_General_Self-Supervised_Keypoint_Detector_CVPR_2022_paper.pdf)【CVPR, 2022】【[code](https://github.com/qq456cvb/UKPGAN)】

##### 2.1.3 Outlier Rejection
- [RANSAC: Random Sample Consensus: A Paradigm for Model Fitting with Applications to Image Analysis and Automated Cartography](http://www.cs.ait.ac.th/~mdailey/cvreadings/Fischler-RANSAC.pdf) 【1981】
- [TEASER: Fast and Certifiable Point Cloud Registration](https://arxiv.org/abs/2001.07715) 【T-RO, 2020】【[code](https://github.com/MIT-SPARK/TEASER-plusplus)】
- [SC^2-PCR: A Second Order Spatial Compatibility for Efficient and Robust Point Cloud Registration](https://arxiv.org/abs/2203.14453)【CVPR, 2022】【[code](https://github.com/ZhiChen902/SC2-PCR)】

### 3.Fine Registration (Local Registration)


### 4.Datasets
- [3DMatch](http://3dmatch.cs.princeton.edu/)
- [KITTI Odometry](http://www.cvlibs.net/datasets/kitti/eval_odometry.php)
- [ETH (Challenging data sets for point cloud registration algorithms)](https://projects.asl.ethz.ch/datasets/doku.php?id=laserregistration:laserregistration)
- [WHU-TLS Benchmark](http://3s.whu.edu.cn/ybs/en/benchmark.htm)
- [ModelNet](https://modelnet.cs.princeton.edu/)
- [A Benchmark for Point Clouds Registration Algorithms](https://github.com/iralabdisco/point_clouds_registration_benchmark)
- [Standford 3DScanning](http://graphics.stanford.edu/data/3Dscanrep/)


### 5.Tools
- [Open3D: A Modern Libray for 3D Data Processing](http://www.open3d.org/docs/release/index.html)
- [PCL: Point Cloud Library](https://pointclouds.org/)
- [Pytorch Geometric](https://github.com/rusty1s/pytorch_geometric)
- [PyTorch Points 3D](https://github.com/nicolas-chaulet/torch-points3d)
- [probreg](https://github.com/neka-nat/probreg)
