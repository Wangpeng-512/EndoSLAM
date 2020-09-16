# EndoSLAM Dataset and An Unsupervised Monocular Visual Odometry and Depth Estimation Approach for Endoscopic Videos: Endo-SfMLearner
<p align="center">
<img align="center"  src='imgs/EndoSLAM_Logo.jpeg' width=456/> 
</p>

## EndoSLAM Dataset Overview

<p align="center">
  <img src="imgs/ply2.gif" alt="ply" />
</p>

We introduce an endoscopic SLAM dataset which consists of  standard as well as capsule endoscopy recordings. The dataset is divided into 35 sub-datasets. Specifically, 18, 5 and 12 sub-datasets exist for colon, small intestine and stomach respectively.

 - To the best of authors' knowledge, this is the very first dataset published to be used in capsule endoscopy SLAM tasks, with timed 6 DoF pose data and high precision 3D map ground truth
  - Two different capsules and conventional endoscope cameras, with high and low resolution were used, so as to generate variety in camera specifications and lighting conditions. Images from different cameras with various resolutions for same organs and depth for each related organs are further unique features of the proposed dataset. We also provide images and pose values for two types of wireless endoscopes, which differ from each other in certain aspects like camera resolution, frame rate, and diagnostic results for detecting Z-line, duodenal papillae and bleeding.
  - Some of the sub-datasets include the same trajectories in two versions, e.g with and without polyps so that effect of having polyps as distinguishable features in the organ environment can be analysed, as well. 
  
The dataset is publicly available in [DropBox](https://www.dropbox.com/sh/l8n581q0ia97u31/AACDzAkd1Zlb3KY6dVarOMw8a?dl=0).

### 1. Dataset Shooting

The experimental procedure is demonstrated at [YouTube](https://www.youtube.com/watch?v=G_LCe0aWWdQ).

### 2. Collection of frames taken on endoscope trajectories

Illustration of recorded frames are as following:

<p align="center">
<img src='imgs/camsamplesnew4.png' width=800/> 
</p>

The ex-vivo and synthetic parts of dataset consist of a total of 42,700 and 21,887 frames respectively. The specifications of dataset parts recorded from each camera are as follows: 

<p align="center">

|     Parts    |# of Frames | FPS  | Resolution |
|--------------|------------|------|------------|
| HighCam      | 21,428     | 20   |1280 x 720  | 
| LowCam       | 17,978     | 20   | 640 x 480  | 
| Pillcam      | 239        |4 - 35| 256 x 256  | 
| MiroCam      | 3,055      | 3    | 320 x 320  | 
| UnityCam     | 21,887     | 30   | 320 x 320  | 
</p>
 
### 3. Dataset Organization

<p align="left">
<img src='imgs/datatree.png' width=520/> 
</p>
<p align="center">
<img src='imgs/EndoSfMLogo.jpeg' width=356/> 
</p>



## Endo-SfMLearner Overview

We introduce Endo-SfMLearner framework as self-supervised spatial attantion-based monocular depth and pose estimation method.

Our main contributions are as follows:
- Brightness-aware photometric loss, which makes the predicted depth to be consistent under various illumination condition.
- Spatial attention based pose network which is optimized for capsule endoscopy images. 

<p align="center">
<img src='imgs/architecture.png' width=356/> 
</p>

## Getting Started

### 1. Installation

#### Clone Endo-SfMLearner Repository

```bash
cd ~
git clone https://github.com/CapsuleEndoscope/EndoSLAM
cd Endo-SLAM
```

#### Prerequisities

 To use the EndoSFM, you will need to:

```bash
pip3 install -r requirements.txt
```

### 2. Pretrained Models

Pretrained models (Endo-SfMLearner) can be downloaded [here!]()

### 3. Use-Cases of Endo-SfMLearner with EndoSLAM Dataset

#### 3.1 Depth Estimation

<p align="center">
<img src='imgs/real_stom_depth_fig.png' width=800/> 
</p>

<p align="center">
<img src='imgs/unity_stom_depth_fig.png' width=800/> 
</p>

<p align="center">

|     Unity       |Endo-SfMLearner | SC-SfMLearner| Monodepth2 | Monodepth2 pretrained | SfMLearner | SfMLearner pretrained |
|-----------------|----------------|--------------|------------|-----------------------|------------|-----------------------|
| RMSE(mean,stdev)| 0.3148 , 0.0685|0.3692 , 0.0779|0.3322 , 0.0815|0.4531 , 0.1011|0.8779 , 0.0908|0.4382 , 0.0782|


</p>

#### 3.2 Pose Estimation

<p align="center">
<img src='imgs/real_pose.png' width=800/> 
</p>


#### 3.3 3D Map Reconstruction





 
## Reference

If you find our work useful in your research or if you use parts of this code please consider citing our paper:

```
@article{ozyoruk2020quantitative,
  title={Quantitative Evaluation of Endoscopic SLAM Methods: EndoSLAM Dataset},
  author={[dataset] Ozyoruk, Kutsev Bengisu and Gokceler, Guliz Irem and Incetan, Kagan and Coskun, Gulfize and Almalioglu, Yasin and Mahmood, Faisal and Durr, Nicholas J and Curto, Eva and Perdigoto, Luis and Oliveira, Marina and others},
  journal={arXiv preprint arXiv:2006.16670},
  year={2020}
}
```



<!-- 





## Help

- [Frequently Asked Questions](#frequently-asked-questions)
- [Limitations](#limitations)

-->