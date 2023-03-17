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
- [Deep learning based point cloud registration: an overview](https://www.sciencedirect.com/science/article/pii/S2096579620300383) 【Virtual Reality & Intelligent Hardware, 2020】
- [A comprehensive survey on point cloud registration](https://arxiv.org/pdf/2103.02690) 【arXiv, 2021】
- [A review of non-rigid transformations and learning-based 3D point cloud registration methods](https://www.sciencedirect.com/science/article/pii/S0924271622003380)【ISPRS Journal of Photogrammetry and Remote Sensing, 2023】


### 2.Coarse Registration

#### 2.1 Feature Matching Based
##### 2.1.1 Feature Description
###### (1) Point-based Strategy
- [D3Feat: Joint Learning of Dense Detection and Description of 3D Local Features](https://arxiv.org/abs/2003.03164) 【CVPR, 2020】【[code](https://github.com/XuyangBai/D3Feat)】

###### (2) Voxel-based Strategy
- [FCGF: Fully Convolutional Geometric Features](https://openaccess.thecvf.com/content_ICCV_2019/papers/Choy_Fully_Convolutional_Geometric_Features_ICCV_2019_paper.pdf) 【ICCV, 2019】【[code](https://github.com/chrischoy/FCGF)】

###### (3) Point-Voxel Strategy

###### (4) Line-based Strategy
- [SuperLine3D: Self-supervised Line Segmentation and Description for LiDAR Point Cloud](https://arxiv.org/pdf/2208.01925)【ECCV, 2022】【[code](https://github.com/zxrzju/SuperLine3D)】

###### (5) Other Strategy

##### 2.1.2 Keypoint Detection
##### 2.1.3 Outlier Rejection

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
