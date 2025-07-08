# YOLO detector and SOTA Multi-object tracker Toolbox

```bash 
git https://github.com/GuangZhouTaDaRen/YOLO-OCSORT.git


🙌 ***If you have any suggestions for adding trackers***, please leave a comment in the Issues section with the paper title or link! Everyone is welcome to contribute to making this repo better.

<div align="center">

**Language**: English 

</div>

## 🗺️ Latest News

- ***2025.07.08*** 

## ❤️ Introduction

This repo is a toolbox that implements the **tracking-by-detection paradigm multi-object tracker**. The detector supports:

- YOLOX 
- YOLO v7
- YOLO v8, 
- YOLO 11, 

and the tracker supports:

- SORT
- DeepSORT 
- ByteTrack ([ECCV2022](https://arxiv.org/pdf/2110.06864))
- Bot-SORT ([arxiv2206](https://arxiv.org/pdf/2206.14651.pdf))
- OCSORT ([CVPR2023](https://openaccess.thecvf.com/content/CVPR2023/papers/Cao_Observation-Centric_SORT_Rethinking_SORT_for_Robust_Multi-Object_Tracking_CVPR_2023_paper.pdf))
- C_BIoU Track ([arxiv2211](https://arxiv.org/pdf/2211.14317v2.pdf))
- Strong SORT ([IEEE TMM 2023](https://arxiv.org/pdf/2202.13514))
- Sparse Track ([arxiv 2306](https://arxiv.org/pdf/2306.05238))
- UCMC Track ([AAAI 2024](http://arxiv.org/abs/2312.08952))
- Hybrid SORT([AAAI 2024](https://ojs.aaai.org/index.php/AAAI/article/view/28471))
and the reid model supports:

- OSNet
- Extractor from DeepSort

The highlights are:
- Supporting more trackers than MMTracking
- Rewrite multiple trackers with a ***unified code style***, without the need to configure multiple environments for each tracker 
- Modular design, which ***decouples*** the detector, tracker, reid model and Kalman filter for easy conducting experiments

![gif](figure/demo.gif)


##  🔨 Installation

The basic env is:

- Python：3.10, Pytorch: 2.1.1

Run following commond to install other packages:

```bash
pip3 install -r requirements.txt
```


```
dataset_name
     |---images
           |---train
                 |---sequence_name1
                             |---000001.jpg
                             |---000002.jpg ...
           |---val ...
           |---test ...

     |

```


***Then, you need to prepare a `yaml` file to indicate the path so that the code can find the images.***

Some examples are in `tracker/config_files`. The important keys are:

```
DATASET_ROOT: '/data/xxxx/datasets/MOT17'  # your dataset root
SPLIT: test  # train, test or val
CATEGORY_NAMES:  # same in YOLO training
  - 'Tuta absoruta'

CATEGORY_DICT:
  0: 'Tuta absoruta'
```



### 🏃 Training 


```
python tracker/yolov11_utils/train_yolov11.py
```


### 😊 Tracking !

For example:

```
python tracker/track.py 
```

