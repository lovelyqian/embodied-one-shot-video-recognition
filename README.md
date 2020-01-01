# Embodied-One-Shot-Video-Recognition
The code of paper ACM Multimedia 2019: "Embodied One-Shot Video Recognition: Learning from Actions of a Virtual Embodied Agent"

- paper link: https://dl.acm.org/citation.cfm?id=3351015
- UnrealAction dataset link: http://www.sdspeople.fudan.edu.cn/fuyanwei/dataset/UnrealAction/

# Introduction
One-shot learning aims to recognize novel target classes from few examples by transferring knowledge from source classes, under a
general assumption that the source and target classes are semantically related but not exactly the same. Based on this assumption,
recent work has focused on image-based one-shot learning, while little work has addressed video-based one-shot learning. One of the
challenges lies in that it is difficult to maintain the disjoint-class assumption for videos, since video clips of target classes may potentially
appear in the videos of source classes. 

### embodied one shot video recognition
To address the issue, we introduce a novel setting, termed as embodied agents based one-shot learning, which leverages synthetic videos produced in a virtual
environment to understand realistic videos of target classes. In this setting, we further propose two types of learning tasks: embodied
one-shot video domain adaptation and embodied one-shot video transfer recognition. These tasks serve as a testbed for evaluating
video related one-shot learning tasks. 

![Image text](https://github.com/lovelyqian/Embodied-One-Shot-Video-Recognition/blob/master/images/embodied-one-shot-video-recognition.png)

### UnrealAction dataset
We also construct a dataset termed as UnrealAction. All the source videos in  UnrealAction are generated by virtual agents.

UnrealAction contains 14 actions, and for each action it has 100 virtual source videos and 10 real target videos.

![Image text](https://github.com/lovelyqian/Embodied-One-Shot-Video-Recognition/blob/master/images/unrealAction.png)

### video segment augmentation method
In addition, we propose a general video segment augmentation method as follows.

![Image text](https://github.com/lovelyqian/Embodied-One-Shot-Video-Recognition/blob/master/images/video_augmentation_method.png)

# Usage
**0. modify the global path**
- modify code: `utils.py`

**1. finetune model on source data**
- run code: `network_train.py`

**2. augment source data**
- run code: `generate_augmented_datasets.py`

**3. finetune model on the augmented data**
- run code: `network_train.py`
- change the mode to `aug_seg_T`

**4. test model with/without applying augmentation method**
- run code: `network_test.py`
- without augmentation methof: `test_network_baseline()`
- with augmentation method: `test_network_aug_segment()`


# Citing
If you find this code useful for your research, please consider citing the following paper:
```
@inproceedings{fu2019embodied,
  title={Embodied One-Shot Video Recognition: Learning from Actions of a Virtual Embodied Agent},
  author={Fu, Yuqian and Wang, Chengrong and Fu, Yanwei and Wang, Yu-Xiong and Bai, Cong and Xue, Xiangyang and Jiang, Yu-Gang},
  booktitle={Proceedings of the 27th ACM International Conference on Multimedia},
  pages={411--419},
  year={2019},
  organization={ACM}
}
```
