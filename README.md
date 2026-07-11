# Adaptive Spatio-Temporal Keyframe Selection for Efficient Violence Detection in Surveillance Video

**Official implementation of the manuscript:**

**"Adaptive Spatio-Temporal Keyframe Selection for Efficient Violence Detection in Surveillance Video"**

---

## Authors

**Akram Rahmani¹, Seyfollah Soleimani²***  

¹ Department of Computer Engineering, Faculty of Engineering, Arak University, Arak, Iran  
²* Department of Computer Engineering, Faculty of Engineering, Arak University, Arak, Iran  

**Corresponding Author:**  
**Seyfollah Soleimani**  
Email: s-soleimani@araku.ac.ir  

---

## Publication Status

This manuscript has been submitted to **The Visual Computer journal** and is currently **under peer review**.

---

# Overview

Violence detection in surveillance videos is a challenging computer vision problem with important applications in intelligent monitoring systems, public safety, and automated security analysis. Real-world surveillance videos usually contain large amounts of redundant visual information caused by unchanged backgrounds, irrelevant frames, illumination variations, occlusions, camera movements, and complex human interactions. Processing all video frames increases computational requirements and limits the efficiency of practical violence detection systems.

This repository provides the official implementation of the proposed framework:

**Adaptive Spatio-Temporal Keyframe Selection for Efficient Violence Detection in Surveillance Video**

The proposed method introduces an efficient violence detection framework based on **adaptive spatio-temporal keyframe selection** and deep feature learning. Instead of processing all available frames, the framework automatically identifies the most informative frames by analyzing both spatial visual characteristics and temporal variations. This strategy reduces redundant information while preserving important visual and motion patterns required for accurate violence recognition.

The selected keyframes are processed using a pretrained **EfficientNet-B0** network to extract discriminative spatial representations. The generated feature sequences are then modeled using a **Bidirectional Gated Recurrent Unit (BiGRU)** network to capture temporal relationships among consecutive keyframes. Finally, a fully connected classification module predicts whether the input video contains a violent or non-violent event.

The main objective of this framework is to achieve an effective balance between **classification accuracy and computational efficiency** by reducing unnecessary frame processing while maintaining essential spatial and temporal information.


---

# Overall Algorithm Pipeline

The proposed framework consists of four main stages:

### 1. Video Preprocessing and Adaptive Keyframe Selection

Input surveillance videos are first converted into frame sequences. An adaptive spatio-temporal selection strategy is then applied to identify representative keyframes. The selection process considers both visual information and temporal changes between consecutive frames, allowing the model to focus on the most informative parts of the video while eliminating redundant frames.


### 2. Spatial Feature Extraction

The selected keyframes are passed through a pretrained **EfficientNet-B0** model. This network extracts compact and discriminative spatial features representing visual patterns related to violent and non-violent activities.


### 3. Temporal Feature Modeling

The extracted feature sequences are provided to a **BiGRU** network. By analyzing the sequence in both forward and backward directions, BiGRU learns temporal dependencies and motion patterns associated with violent events.


### 4. Video-Level Classification

The learned spatial-temporal representations are finally passed through fully connected layers with a sigmoid classifier to perform binary video classification:

- **Violent**
- **Non-Violent**


The complete processing pipeline is summarized as:

```
Input Video
      |
      ↓
Frame Extraction and Preprocessing
      |
      ↓
Adaptive Spatio-Temporal Keyframe Selection
      |
      ↓
Selected Informative Keyframes
      |
      ↓
EfficientNet-B0 Spatial Feature Extraction
      |
      ↓
Temporal Feature Sequence
      |
      ↓
BiGRU Temporal Modeling
      |
      ↓
Fully Connected Classification
      |
      ↓
Violence / Non-Violence Prediction
```


---

# Datasets

The proposed framework is evaluated on three benchmark violence detection datasets:

- **AIRTLab Dataset**
- **Hockey Fight Dataset**
- **Real-Life Violence Situations (RLVS) Dataset**


---

# Experimental Results

The proposed method achieves competitive performance while significantly reducing redundant frame processing.

| Dataset | Accuracy |
|---------|----------|
| AIRTLab | 92.29% |
| Hockey Fight | 97.00% |
| RLVS | 97.01% |


The results demonstrate that adaptive keyframe selection can reduce computational cost while preserving the discriminative spatial and temporal information required for reliable violence detection.


---

# Repository Structure

```
├── AIRTLab_Results
│   └── Experimental results on AIRTLab dataset
│
├── Hockey_Fight_Results
│   └── Experimental results on Hockey Fight dataset
│
├── RLVS_Results
│   └── Experimental results on RLVS dataset
│
├── Codes
│   └── Implementation and evaluation codes
│
├── Pretrained Weights
│   └── Trained model weights
│
└── README.md
```


---

# Pretrained Weights

The repository provides pretrained weights of the proposed framework, including the trained parameters of the spatial feature extraction module, temporal modeling network, and classification layers.

These weights can be used to reproduce the reported experimental results and evaluate the proposed approach on supported datasets.


---

# Main Contributions

The main contributions of this work are:

- An adaptive spatio-temporal keyframe selection strategy for efficient violence detection.
- Integration of EfficientNet-B0 and BiGRU for spatial-temporal video representation learning.
- Reduction of redundant frame processing while preserving important violent-event information.
- An efficient framework suitable for surveillance video analysis.
- Comprehensive evaluation on multiple benchmark violence detection datasets.


---

# Citation

If you use this repository or the proposed method in your research, please cite:

```bibtex
@article{rahmani2026adaptive,
title={Adaptive Spatio-Temporal Keyframe Selection for Efficient Violence Detection in Surveillance Video},
author={Rahmani, Akram and Soleimani, Seyfollah},
journal={The Visual Computer},
note={Under Review},
year={2026}
}
```


---

# Contact

**Seyfollah Soleimani**  
Department of Computer Engineering  
Arak University, Iran  

Email:  
s-soleimani@araku.ac.ir
