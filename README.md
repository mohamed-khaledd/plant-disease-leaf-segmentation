#  Plant Disease Detection and Leaf Segmentation
A deep learning-based computer vision project that performs leaf segmentation and disease classification from plant images to support early diagnosis and crop health monitoring.
## Table of Contents
- [Project Overview](#project-overview)
- [Part 1 – Classification (DenseNet121 / VGG16)](#part-1--classification-densenet121--vgg16)
- [Part 2 – Segmentation (U-Net)](#part-2--segmentation-u-net)
- [Part 3 – Demo Pipeline](#part-3--demo-pipeline)
- [Team Members](#team-members)
  
# Project Overview
This project is divided into three main parts:

1. Plant Disease Classification – Detect whether a plant is healthy or infected using enseNet121 and VGG16.

2. Leaf Disease Segmentation – Localize infected regions on leaves using a U-Net-based semantic segmentation model.

3. Integrated Demo Pipeline – A demo notebook that combines classification and segmentation for full disease detection and visualization.

#  Part 1 – Classification (DenseNet121 / VGG16)
This notebook focuses on detecting the type of disease in a given leaf image using transfer learning.

## Goals:
Classify leaves into 15 categories (healthy/diseased).

* Use PlantVillage Dataset.

* Train models using DenseNet121 and VGG16 (pretrained on ImageNet).

* Apply data augmentation, normalization, and early stopping.

## Datasets:
[Kaggle](https://www.kaggle.com/datasets/emmarex/plantdisease)

### Description:
A large dataset containing over 20,000 images of healthy and diseased plant leaves across 15 classes.

### Use Case:
Used to train and evaluate the classification model that detects the disease class of a given leaf image.

### Class List

The classification model is trained to recognize 15 distinct classes, including both healthy and diseased leaves from three plant types: Tomato, Potato, and Pepper.


| Label Index | Class Name                                        |
|-------------|---------------------------------------------------|
| 0           | Pepper__bell___Bacterial_spot                     |
| 1           | Pepper__bell___healthy                            |
| 2           | Potato___Early_blight                             |
| 3           | Potato___Late_blight                              |
| 4           | Potato___healthy                                  |
| 5           | Tomato_Bacterial_spot                             |
| 6           | Tomato_Early_blight                               |
| 7           | Tomato_Late_blight                                |
| 8           | Tomato_Leaf_Mold                                  |
| 9           | Tomato_Septoria_leaf_spot                         |
| 10          | Tomato_Spider_mites_Two_spotted_spider_mite       |
| 11          | Tomato__Target_Spot                               |
| 12          | Tomato__Tomato_YellowLeaf__Curl_Virus             |
| 13          | Tomato__Tomato_mosaic_virus                       |
| 14          | Tomato_healthy                                    |

## Best Model: DenseNet121
* Accuracy: 95%

* F1-score (macro avg): 0.94

## Sample Metrics:
| Model       | Accuracy | Macro F1-score |
| ----------- | -------- | -------------- |
| VGG16       | 93%      | 0.92           |
| DenseNet121 | **95%**  | **0.94**       |

# Part 2 – Segmentation (U-Net)

We performs semantic segmentation to highlight diseased areas on the leaf surface using a U-Net architecture.

## Goals:
* Detect pixel-level infected areas.

* Visualize disease severity and spread.

* Assist in precise diagnosis and treatment planning.

## Datasets:
[Kaggle](https://www.kaggle.com/datasets/fakhrealam9537/leaf-disease-segmentation-dataset)
- **Description**:
  
  This dataset contains 588 plant leaf images showing disease symptoms, along with their corresponding segmentation masks (588 masks). 
  
  Each mask highlights the infected regions of the leaf (disease vs. background).

- **Use Case**:
  
  Used to train and validate the U-Net segmentation model to detect diseased areas at the pixel level.

- **Augmented Data:**
  
  We used the pre-augmented data provided in the aug_data folder of the dataset. This includes:

  - 2940 total images

  - 2940 corresponding masks

## Workflow:
- Data preprocessing & augmentation.

- U-Net model training.

- Visual evaluation of predicted masks.

- Saving the best model for inference.

# Part 3 – Demo Pipeline
A fully integrated notebook simulating a real-world tool for plant disease detection.

## What it Does:
- Loads pre-trained classification and segmentation models.

- Predicts disease type with confidence score.

- Generates a visual segmentation mask.

- Displays both results together for fast diagnosis.


# Team Members

| Name           | GitHub                                                 |
| -------------- | ------------------------------------------------------ |
| Mohamed Khaled | [@mohamed-khaledd](https://github.com/mohamed-khaledd) |
| Amr Wahidi     | [@amr10w](https://github.com/amr10w)                   |

