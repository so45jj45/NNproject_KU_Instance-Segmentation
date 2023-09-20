# Project: Discovering objects in images and distinguish the instances of objects


## Projcect introduction (Instance Segmentation)

### Task introduction
Segmentation plays a central role in a broad range of applications, including medical image analysis, autonomous vehicles, and video surveillance. To achieve generalized scene analysis, the ability to distinguish between instances of objects is required. Image segmentation is an essential component in many visual understanding systems. It involves partitioning images (or video frames) into multiple segments or objects.



## Installation

First install Detectron2 following the official guide: [INSTALL.md](https://github.com/facebookresearch/detectron2/blob/master/INSTALL.md).

*Please use Detectron2 with commit id [9eb4831](https://github.com/facebookresearch/detectron2/commit/9eb4831f742ae6a13b8edb61d07b619392fb6543) if you have any issues related to Detectron2.*

## Models
### COCO Instance Segmentation Baselines

Model | Name | inf. time | box AP | mask AP | download
--- |:---|:---:|:---:|:---:|:--:|
Mask R-CNN |[R_50_1x](https://github.com/facebookresearch/detectron2/blob/master/configs/COCO-InstanceSegmentation/mask_rcnn_R_50_FPN_1x.yaml) | 13 FPS | 38.6 | 35.2 |
Mask R-CNN |[R_50_3x](https://github.com/facebookresearch/detectron2/blob/master/configs/COCO-InstanceSegmentation/mask_rcnn_R_50_FPN_3x.yaml) | 13 FPS | 41.0 | 37.2 | 
Mask R-CNN |[R_101_3x](https://github.com/facebookresearch/detectron2/blob/master/configs/COCO-InstanceSegmentation/mask_rcnn_R_101_FPN_3x.yaml) | 10 FPS | 42.9 | 38.6 |
