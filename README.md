# Project: Discovering objects and distinguish the instances of objects in images (Instance Segmentation)

## Motivation
Image segmentation is one of the major tasks in the field of computer vision. Currently, image segmentation is used in a wide range of fields, such as medical image analysis, autonomous driving, security, satellites, and aerial photography, and it is expected to be used in even more fields in the future. Concomitant with increasing interest in the foreground and distinguishing identical instances within the same class, instance segmentation is actively being researched
To achieve generalized scene analysis, the ability to distinguish between instances of objects is required, and so concomitant with increasing interest in the foreground and distinguishing identical instances within the same class, instance segmentation is actively being researched. 

While extensive research is being conducted, the task of detecting and distinguishing objects in complex and diverse real-world scenarios remains a challenging problem.


### Objective
The goal of instance segmentation is to produce a pixel-wise segmentation map of the image, where each pixel is assigned to a specific object instance.

### Example
![image](https://github.com/so45jj45/NNproject_KU_Instance-Segmentation/assets/80938806/207fc8c7-06c2-4ea6-9ca6-e99c4df798cb)


## Dataset description (COCO)

The COCO object detection dataset is a large-scale image dataset designed to advance state-of-the-art techniques for the object detection task. Many researches used the
MS COCO 2017 instance segmentation dataset. This dataset includes 118K/5K images for train/val with 80 class instance labels. Typically, to conveniently evaluate models, the evaluation is carried out on a validation dataset.

The dataset is available for download on the official COCO website. (However, please note that clicking the link does not work on the Windows OS, but it can be downloaded using "wget" on the Ubuntu OS.)

2017 training set: http://images.cocodataset.org/zips/train2017.zip

2017 validation set: http://images.cocodataset.org/zips/val2017.zip

2017 train/val annotations: http://images.cocodataset.org/annotations/annotations_trainval2017.zip


## Baseline for understand the project

To help with understanding the project, i will introduce the most famous model(Mask R-CNN) used in the project.
https://github.com/facebookresearch/detectron2/blob/main/MODEL_ZOO.md


### Requirements
Linux or macOS with Python ≥ 3.7
PyTorch ≥ 1.8 and torchvision that matches the PyTorch installation. Install them together at pytorch.org to make sure of this
OpenCV is optional but needed by demo and visualization
Anaconda environment

### Installation
I followed the official guide of Detectron2: [INSTALL.md](https://github.com/facebookresearch/detectron2/blob/master/INSTALL.md).

My workstation environment is as below

Ubuntu 20.04

CUDA 11.3

Anaconda environment

#### Create conda environment
```
conda create -n maskrcnn python==3.8
conda activate maskrcnn
```

#### Install the pytorch
```
conda install pytorch==1.12.0 torchvision==0.13.0 torchaudio==0.12.0 cudatoolkit=11.3 -c pytorch
(Please install PyTorch on your workstation environment according to your needs)
```

#### Install the Detecron2
```
python3 -m pip install -U 'git+https://github.com/facebookresearch/detectron2.git@ff53992b1985b63bd3262b5a36167098e3dada02'
```

#### Prepare dataset and pre-trained model
```
git clone https://github.com/facebookresearch/detectron2.git

(You must place the COCO dataset to "local_path"/detectron2/datasets")

Ex)
local_path/detectron2/datasets/coco/val2017
local_path/detectron2/datasets/coco/train2017
local_path/detectron2/datasets/coco/anotations

You can download pre-trained models from below github site
And make directory to save models in detectron2 root folder

Ex)
local_path/detectron2/"saved_model_folder"
```


### Training
```
python tools/train_net.py \
  --config-file ../configs/COCO-InstanceSegmentation/mask_rcnn_R_50_FPN_1x.yaml \
  --num-gpus 1 SOLVER.IMS_PER_BATCH 2 SOLVER.BASE_LR 0.0025
```

### Evaluation
```
python tools/train_net.py \
  --config-file configs/COCO-InstanceSegmentation/mask_rcnn_R_101_FPN_3x.yaml \
  --eval-only
  MODEL.WEIGHTS saved_model_folder/model_final_a3ec72.pkl
```

Here is my evaluation results

Evaluation results for bbox: 
|   AP   |  AP50  |  AP75  |  APs   |  APm   |  APl   |
|:------:|:------:|:------:|:------:|:------:|:------:|
| 42.932 | 63.330 | 46.872 | 26.402 | 46.627 | 56.114 |

Evaluation results for segm: 
|   AP   |  AP50  |  AP75  |  APs   |  APm   |  APl   |
|:------:|:------:|:------:|:------:|:------:|:------:|
| 38.634 | 60.449 | 41.294 | 19.489 | 41.340 | 55.350 |

(Please note that the score may vary slightly depending on the version of PyTorch)

### Inference
```
python demo/demo.py \
  --config-file configs/COCO-InstanceSegmentation/mask_rcnn_R_101_FPN_3x.yaml
  --input datasets/coco/val2017/*.jpg
  --output result/
  --opts MODEL.WEIGHTS models/model_final_a3ec72.pkl
```

### Mask R-CNN pre-trained model

Model | Name | inf. time | box AP | mask AP | download
--- |:---|:---:|:---:|:---:|:--:|
Mask R-CNN |[R_50_1x](https://github.com/facebookresearch/detectron2/blob/master/configs/COCO-InstanceSegmentation/mask_rcnn_R_50_FPN_1x.yaml) | 13 FPS | 38.6 | 35.2 |
Mask R-CNN |[R_50_3x](https://github.com/facebookresearch/detectron2/blob/master/configs/COCO-InstanceSegmentation/mask_rcnn_R_50_FPN_3x.yaml) | 13 FPS | 41.0 | 37.2 | 
Mask R-CNN |[R_101_3x](https://github.com/facebookresearch/detectron2/blob/master/configs/COCO-InstanceSegmentation/mask_rcnn_R_101_FPN_3x.yaml) | 10 FPS | 42.9 | 38.6 |

You can also find various pre-trained models from below Detectron2 official github
https://github.com/facebookresearch/detectron2/blob/main/MODEL_ZOO.md
