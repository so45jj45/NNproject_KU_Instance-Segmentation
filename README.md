# Project: Discovering objects and distinguish the instances of objects in images (Instance Segmentation)

## Motivation
Image segmentation is one of the major tasks in the field of computer vision. Currently, image segmentation is used in a wide range of fields, such as medical image analysis, autonomous driving, security, satellites, and aerial photography, and it is expected to be used in even more fields in the future. Concomitant with increasing interest in the foreground and distinguishing identical instances within the same class, instance segmentation is actively being researched
To achieve generalized scene analysis, the ability to distinguish between instances of objects is required, and so concomitant with increasing interest in the foreground and distinguishing identical instances within the same class, instance segmentation is actively being researched. 

While extensive research is being conducted, the task of detecting and distinguishing objects in complex and diverse real-world scenarios remains a challenging problem.


### Objective
The goal of instance segmentation is to produce a pixel-wise segmentation map of the image, where each pixel is assigned to a specific object instance.

### Example
![image](https://github.com/so45jj45/NNproject_KU_Instance-Segmentation/assets/80938806/8dd0e398-0497-4065-9f4a-53a86bf2986b)



## Dataset description (COCO)

The COCO object detection dataset is a large-scale image dataset designed to advance state-of-the-art techniques for the object detection task. Many researches used the
MS COCO 2017 instance segmentation dataset. This dataset includes 118K/5K images for train/val with 80 class instance labels. Typically, to conveniently evaluate models, the evaluation is carried out on a validation dataset.

The dataset is available for download on the official COCO website. (However, please note that clicking the link does not work on the Windows OS, but it can be downloaded using "wget" on the Ubuntu OS.)

2017 training set: http://images.cocodataset.org/zips/train2017.zip

2017 validation set: http://images.cocodataset.org/zips/val2017.zip

2017 train/val annotations: http://images.cocodataset.org/annotations/annotations_trainval2017.zip


## Baseline for understand the project

To help with understanding the project, we introduce the most famous model(Mask R-CNN) used in the project.
https://github.com/facebookresearch/detectron2/blob/main/MODEL_ZOO.md

###Installation

First install Detectron2 following the official guide: [INSTALL.md](https://github.com/facebookresearch/detectron2/blob/master/INSTALL.md).

## Models
### Mask R-CNN pretrained model

Model | Name | inf. time | box AP | mask AP | download
--- |:---|:---:|:---:|:---:|:--:|
Mask R-CNN |[R_50_1x](https://github.com/facebookresearch/detectron2/blob/master/configs/COCO-InstanceSegmentation/mask_rcnn_R_50_FPN_1x.yaml) | 13 FPS | 38.6 | 35.2 |
Mask R-CNN |[R_50_3x](https://github.com/facebookresearch/detectron2/blob/master/configs/COCO-InstanceSegmentation/mask_rcnn_R_50_FPN_3x.yaml) | 13 FPS | 41.0 | 37.2 | 
Mask R-CNN |[R_101_3x](https://github.com/facebookresearch/detectron2/blob/master/configs/COCO-InstanceSegmentation/mask_rcnn_R_101_FPN_3x.yaml) | 10 FPS | 42.9 | 38.6 |
