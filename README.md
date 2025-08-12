# Flower Detector

**Project Goal:** Develop a supervised object detection model using YOLO to accurately identify and localise various types of flowers in images.

**Programming Language:** Python

 **Model:** YOLO (You Only Look Once)

**Evaluation Metrics:** Precision, Recall, mAP50, mAP50-95

**Best Results:** Precision: 0.795, Recall: 0.831, mAP50: 0.88, mAP50-95: 0.515
<img width="1662" height="685" alt="flower" src="https://github.com/user-attachments/assets/3afb3960-118f-415d-b70c-9a7cdef4a2f5" />
## Overview

**Data Source:** https://universe.roboflow.com/plants-yda3t/plantidentification-eon4y

**Key Data Processing:**
- Merge Roboflow’s given training/validation/test split
1. Direct Resplit
- Group all images in the dataset by class
- Resplit into training/validation/test sets using an 80/10/10 ratio
2. Data Augmentation + Resplit
- Count number of images per class
- Augment underrepresented classes
- Group all images in the dataset by class
- Resplit into training/validation/test sets using an 80/10/10 ratio

**Key Evaluation Steps & Insights:**
- Display images with:
  - Ground truth boxes
  - Prediction boxes (confidence ≥ 0.4)
- Findings:
  - After direct resplit → more even performance across classes
  - Performance for a given class can vary between different resplit rounds
  - After data augmentation + resplit → further improvement in performance
<img width="1877" height="1293" alt="flower1" src="https://github.com/user-attachments/assets/e0c700d4-2b26-4dfc-a05b-7713e7ebcd6c" />

## Files
- `Flower_Detector.ipynb`: Data preprocessing, model training, tuning, and evaluation
- `Flower Detector - Training Iteration Process.pdf`: Documentation of training iteration process
- `best.pt`: Model's weights from epoch that had best performance on validation set
- `last.pt`: Model's weights from final epoch
- `README.md`: Project overview
