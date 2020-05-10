**Abnormality Detection with Multi-Adaptive Vehicle Detectors
for Traffic Video Analysis**

This is the source code for Track 3 Ai City Challenge 2019.

Extract Road Mask: `Tools/mask_creating.py`

Extract Unchanged Scenes: `Scene-Change-Stop-Detection`

Training Retina Net: `Detectron`

Preprocessing data: [link](https://drive.google.com/file/d/1sPRjyGdU1rBI3a75EatsMPx5SWyCT7GM/view?usp=sharing)

**Testing**

To reduce the testing time: 

- We saved all unchanged scene intervals in json format.

- We saved the result of day/night detector and hard code in `Detectors.py`

- We saved all road masks in npy format.

- We saved all detected bounding boxes. Because we use multiple detectors to finish the task, each one will have specific format to store detected bounding boxes. The code to parse detectors output is in `Detectors.py`

There are 3 classes to parse detector output in `Detectors.py`: Multiple adaptive vehicle detectors by Tran, RetinaNet trained on night videos AICity 2019, FRCNN's Jia Yi Wei, FRCNN trained on dashboard camera datasets.

Link download our result: _Uploading_

To reproduce the result: 
Run `Test.py`: It will takes unchanged scenes, masks, detector result, and external configuration to detect anomalies.

The full result content: 
   
- Images of detected bounding boxes.

- Images of anomaly events and anomaly proposals.

- Confident score for each frames in 2 representations: graph and text

- Detected anomaly events in text: <video_id> <scene_id> <start_time> <end_time> <confident_score>

To merge detected events: Run `ResultRefinement.py`

**Training**

Mulitple Adaptive FRCNN: The training code and model can be found on [HCMUS repository](https://github.com/HCMUS-Smart-Environment-Group/AICItyChallenge2018)

Retina Net: We use the [Detectron](https://github.com/facebookresearch/Detectron) libraries to train model. The modified code inside folder `Detectron`

FRCNN Trained on dashboard camera dataset: We are not allowed to publish this source code because it belongs to other projects (update when available).

FRCNN's Jia Yi Wei: [2018AICITY_MCPRL](https://github.com/NVIDIAAICITYCHALLENGE/2018AICITY_MCPRL)

## Citations
Please consider citing this project in your publications if it helps your research:

```
@Inproceedings{nktuan-AICity2019,
  Title          = {Vehicle Re-identification with Learned Representation and Spatial Verification and Abnormality Detection with Multi-Adaptive Vehicle Detectors for Traffic Video Analysis},
  Author         = {Khac-Tuan Nguyen and Trung-Hieu Hoang and Minh-Triet Tran and Trung-Nghia Le and Ngoc-Minh Bui and Trong-Le Do and Viet-Khoa Vo-Ho and Quoc-An Luong and Mai-Khiem Tran and Thanh-An Nguyen and Thanh-Dat Truong and Vinh-Tiep Nguyen and Minh N. Do},
  BookTitle      = {The IEEE Conference on Computer Vision and Pattern Recognition (CVPR) Workshops},
  Year           = {2019},
}
```

------------------
The code is used for academic purpose only.

