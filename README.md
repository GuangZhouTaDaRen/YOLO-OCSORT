# YOLO-OCSORT

```bash 
git https://github.com/GuangZhouTaDaRen/YOLO-OCSORT.git


🙌 If you have any suggestions for adding trackers***, please leave a comment in the Issues section with the paper title or link! Everyone is welcome to contribute to making this repo better.

**Language**: English 


## 🗺️ Latest News

- ***2025.07.08*** 

##  Introduction

This repo is a toolbox that implements the **tracking-by-detection paradigm multi-object tracker**. The detector supports:

- Improved YOLO 11, 

and the tracker supports:

- Improved OCSORT ([CVPR2023](https://openaccess.thecvf.com/content/CVPR2023/papers/Cao_Observation-Centric_SORT_Rethinking_SORT_for_Robust_Multi-Object_Tracking_CVPR_2023_paper.pdf))


##  Installation

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

