# Awesome-Spatio-temporal-human-action-detection-in-videos

Human spatio-temporal action detection is for answering when (from what time to what time), where (postions), and what actions occur in a given video. It is a crucial ability for selfdriving cars, autonomous care robots, and advanced video search engines. 

This repo is a collection of resources for spatio-temporal human action detection in videos.

![caption](ucf-successful.gif).         ![caption](jhmdb-successful.gif)

Above are demos on action detection. Green boxes are ground-truth. Others are detection results.

## Why Awesome Spatio-temporal Human action detection

Spatio-temporal human action detection in videos is a quite chanllenging task. This repo is tracking the developping of action detection and help to better understand the topic, from datasets, evaluation metrics, and SOTA methods.

**Feedback and contributions are welcome! Please feel free to pull a request for any issues and suggestions.**

## Table of Contents

* [Datasets](#datasets)
   * [Commanly used](#commonly-used)
   * [Potentially Used](#potentially-used)

* [Metrics](#metrics)
   * [Frame-mAP](#frame-map)
   * [Video-mAP](#video-map)

* [Papers](#papers)
   
## Datasets

### Commonly used

* **UCFSports-10**  - contains 10 sport classes in 150 **trimmed videos**.
   * [**paper**] [Action mach a spatio-temporal maximum average correlation height filter for action recognition.](http://cs.ucf.edu/~mikel/ActionMACH.pdf). Rodriguez, Mikel D and Ahmed, Javed and Shah, Mubarak. CVPR 2008.
   * [**website**] [https://www.crcv.ucf.edu/data/UCF_Sports_Action.php](https://www.crcv.ucf.edu/data/UCF_Sports_Action.php). 
   * [**annotation**] You can refer to [ACT-Detector](https://github.com/vkalogeiton/caffe/tree/act-detector) to prepare the dataset.

* **UCF101-24**  -  a subset of UCF101. It contains 24 **sport** classes in 3207 **untrimmed videos**. Each video contains a single action category. Multiple action instances with the same class, but different spatial and temporal boundaries may occur. 
   * [**paper**] [UCF101: A Dataset of 101 Human Actions Classes From Videos in The Wild.](https://arxiv.org/abs/1212.0402). K. Soomro and A. Zamir and M. Shah. 2012.
   * [**website**] [http://www.thumos.info/download.html](http://www.thumos.info/download.html).
   * [**annotation**] The offical annotations for UCF101-24 can be downloaded from [here](http://www.thumos.info/download.html). **Noted** Most recent papers use the corrected version **UCF101-24 v2** from [corrected-UCF101-Annots](https://github.com/gurkirt/corrected-UCF101-Annots) by Gurkirt. You can refer to [ACT-Detector](https://github.com/vkalogeiton/caffe/tree/act-detector) to prepare the dataset.

* **JHMDB51-21**  - contains 21 action categories in 928 **trimmed videos**.
   * [**paper**] [Towards understanding ac- tion recognition.](https://hal.inria.fr/hal-00906902/document).Jhuang, Hueihan and Gall, Juergen and Zuffi, Silvia and Schmid, Cordelia and Black, Michael J. ICCV 2013.
   * [**website**] [http://jhmdb.is.tue.mpg.de](http://jhmdb.is.tue.mpg.de). 
   * [**annotation**] You can refer to [ACT-Detector](https://github.com/vkalogeiton/caffe/tree/act-detector) to prepare the dataset.

* **AVA80-60**  - It has 437 videos with 211k training and 57k validation keyframes sampled one per second. Annotations are provided **per keyframe**. Following [this paper](https://openaccess.thecvf.com/content_cvpr_2018/html/Gu_AVA_A_Video_CVPR_2018_paper.html), the standard protocol is evaluating on 60 classes.
   * [**paper**] [ava: a video dataset of spatiotemporally localized atomic visual actions.](https://openaccess.thecvf.com/content_cvpr_2018/html/Gu_AVA_A_Video_CVPR_2018_paper.html).Gu, Chunhui and Sun, Chen and Ross, David A and Vondrick, Carl and Pantofaru, Caroline and Li, Yeqing and Vijayanarasimhan, Sudheendra and Toderici, George and Ricco, Susanna and Sukthankar, Rahul and others. CVPR 2018.
   * [**website**] [http://research.google.com/ava/](http://research.google.com/ava/). 
   * [**annotation**] You can refer to [ACAR-Net](https://github.com/Siyu-C/ACAR-Net) to prepare the dataset.

### Potentially used

* **VidOR-42** - The dataset is originally used for detecting relations. It provides annotations for action detection but not only for humman actions but also animal actions. The dataset for this task contains 10K user-generated videos and ~69,000 annotated action instances in 42 categories of atomic visual actions (e.g. "watch", "grab", and "hug").
   * [**paper**] [Annotating Objects and Relations in User-Generated Videos.](https://dl.acm.org/doi/abs/10.1145/3323873.3325056).Shang, Xindi and Di, Donglin and Xiao, Junbin and Cao, Yu and Yang, Xun and Chua, Tat-Seng. ICMR 2019.
   * [**website**] [https://videorelation.nextcenter.org/mm19-gdc/task2.html](https://videorelation.nextcenter.org/mm19-gdc/task2.html). 
   * [**annotation**] Refer to [this](https://xdshang.github.io/docs/vidor.html#downloads) for downloading dataset and annotations.

## Metrics

Like object detection, usually **mAP** (mean Average Precision) is used for evaluation. There are two commonly used metrics for evaluating action detection: frame-mAP and video-mAP. 

* **Frame-mAP** does not consider video property. It evaluates mAP based on a single frame. Frame-mAP@IoU=0.5 is mostly reported. (In my own opinion)I cannot to say it is not good for a video task, but it really ignore the temporal and continousing properties of an action.

*  **Video-mAP** caculates mAP based on an actionn tube IoU. Usually, Video-mAP@IoU=0.2, 0.5, 0.75, 0.9 and a mean Video-mAP@0.5:0.95(with step 0.05) are reported.
**Note: High Frame-mAP may not result in high Video-mAP**.

## Papers
