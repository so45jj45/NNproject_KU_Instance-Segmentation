# Project: Discovering objects and distinguish the instances of objects in images (Instance Segmentation)

## Motivation
Segmentation plays a central role in a broad range of applications, including medical image analysis, autonomous vehicles, and video surveillance. To achieve generalized scene analysis, the ability to distinguish between instances of objects is required.

Instance Segmentation is a computer vision task that involves identifying and separating individual objects within an image, including detecting the boundaries of each object and assigning a unique label to each object. 

Detecting and distinguishing objects in complex and diverse real-world scenarios is challenging but a problem worth tackling.


### Objective
The goal of instance segmentation is to produce a pixel-wise segmentation map of the image, where each pixel is assigned to a specific object instance.


![image](https://github.com/so45jj45/NNproject_KU_Instance-Segmentation/assets/80938806/a4f410ef-8909-475b-a083-c6ac9784fefa)


## Dataset description (COCO)


## Baseline for understand the project

To help with understanding the project, we introduce the most famous model(Mask R-CNN) used in the project.

###Installation

First install Detectron2 following the official guide: [INSTALL.md](https://github.com/facebookresearch/detectron2/blob/master/INSTALL.md).

*Please use Detectron2 with commit id [9eb4831](https://github.com/facebookresearch/detectron2/commit/9eb4831f742ae6a13b8edb61d07b619392fb6543) if you have any issues related to Detectron2.*

## Models
### COCO Instance Segmentation Baselines

Model | Name | inf. time | box AP | mask AP | download
--- |:---|:---:|:---:|:---:|:--:|
Mask R-CNN |[R_50_1x](https://github.com/facebookresearch/detectron2/blob/master/configs/COCO-InstanceSegmentation/mask_rcnn_R_50_FPN_1x.yaml) | 13 FPS | 38.6 | 35.2 |
Mask R-CNN |[R_50_3x](https://github.com/facebookresearch/detectron2/blob/master/configs/COCO-InstanceSegmentation/mask_rcnn_R_50_FPN_3x.yaml) | 13 FPS | 41.0 | 37.2 | 
Mask R-CNN |[R_101_3x](https://github.com/facebookresearch/detectron2/blob/master/configs/COCO-InstanceSegmentation/mask_rcnn_R_101_FPN_3x.yaml) | 10 FPS | 42.9 | 38.6 |
