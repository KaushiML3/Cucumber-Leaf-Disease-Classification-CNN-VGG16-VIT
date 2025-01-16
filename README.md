# Cucumber leaf disease classification

Cucumber leaves are susceptible to various diseases, primarily fungal and bacterial. 
Common issues include powdery mildew, which forms white, powdery spots on leaves, 
and downy mildew, characterized by yellow patches and a fuzzy underside.
Anthracnose causes dark, sunken spots on leaves and fruit, while angular leaf spot results in 
water-soaked lesions that become angular and brown.Bacterial wilt, spread by cucumber beetles, 
causes leaves to wilt and die. Proper spacing, crop rotation, and the use of resistant varieties 
can help manage these diseases, along with timely fungicide or bactericide applications.

This repository contains resources for training a deep learning model to classify diseases in 
cucumber leaves. It includes two main Jupyter notebooks for model training,
each implementing a distinct architecture:

- **Custom Architecture Notebook :**
    This notebook demonstrates the use of a custom-built neural network architecture tailored specifically for cucumber leaf disease classification.
    Designed for flexibility and simplicity, the custom architecture allows for experimentation and adaptation to varying datasets.

- **VGG16 Architecture Notebook :**
    Utilizes the pre-trained VGG16 model as a feature extractor or fine-tunes it for the task.
    This notebook leverages transfer learning, enabling efficient training and improved performance by building on the VGG16 model's pre-learned features.

## Features:
1. Preprocessing steps for preparing cucumber leaf images for training and evaluation.
2. Implementation of performance metrics for monitoring model accuracy and loss.
3. Comparisons between custom and VGG16-based models to highlight trade-offs between simplicity and performance.

## Dataset 
The dataset used for training contains 3,754 images of cucumber leaves, divided into three classes representing different disease categories. Each image has a resolution of 1366x768 pixels, providing high-quality data for accurate classification. The dataset is well-suited for deep learning tasks, enabling robust model training and evaluation.

- **Healthy leaf**
- **Powdery mildew**
- **Downy mildew**

[Dataset_Link](https://www.kaggle.com/datasets/kaushigihanml/cucumber-leaf-disease-dataset)


## Notebooks

This folder have two notebooks.One is Custom Architecture Notebook and VGG16 Architecture Notebook.
You can find this notebook in this repository and Kaggle.

- **Kaggle Notyebooks:**
    [Custom Architecture](https://www.kaggle.com/code/kaushigihanml/cucumber-leaf-disease-classification)
    [VGG16 Architecture](https://www.kaggle.com/code/kaushigihanml/cucumber-leaf-disease-classification-vgg16)

## Model Comparison: Custom Architecture vs. VGG16
### Custom Architecture
    - Performance Overview:
        The custom architecture provides a lightweight and flexible solution, designed specifically for cucumber leaf disease classification.

    - Classification Report: 
        Shows reasonable precision, recall, and F1-scores across all three classes. However, it occasionally struggles with class imbalance and misclassification in borderline cases.

                        precision    recall  f1-score   support

        Downy_mildew       0.96      0.96      0.96        23
        Healthy_leaves     1.00      0.88      0.94        17
        Powdery_mildew     0.85      1.00      0.92        11

        accuracy                               0.94        51
        macro avg          0.93      0.95      0.94        51
        weighted avg       0.95      0.94      0.94        51

    - Confusion Matrix: 
        Highlights some overlap between certain classes, with a noticeable number of misclassified samples in specific categories.
![Confusion metrix](https://github.com/KaushiML3/Cucumber-Leaf-Disease-Classification-CNN-VGG16-VIT/blob/main/scr_img/custom.png)

    - Key Strengths:
        Tailored to the dataset, offering a straightforward implementation.
        Requires less computational power compared to pre-trained models.

    - Key Limitations:
        Slightly lower overall accuracy and F1-score compared to the VGG16 model.
        Longer convergence time during training.

### VGG16 Architecture
    - Performance Overview:
        The VGG16 model leverages transfer learning, utilizing pre-trained features for superior classification performance.

    - Classification Report:
        Exhibits higher precision, recall, and F1-scores across all classes. 
  

                        precision    recall  f1-score   support

        Downy_mildew       1.00      0.91      0.95        23
        Healthy_leaves     0.94      1.00      0.97        17
        Powdery_mildew     0.92      1.00      0.96        11

        accuracy                               0.96        51
        macro avg          0.95      0.97      0.96        51
        weighted avg       0.96      0.96      0.96        51

    - Confusion Matrix: 
        Shows significantly fewer misclassified samples, with a more accurate distribution across all classes.

![Confusion metrix](https://github.com/KaushiML3/Cucumber-Leaf-Disease-Classification-CNN-VGG16-VIT/blob/main/scr_img/vgg16.png)

    - Key Strengths:
        High accuracy and robust performance, especially on complex patterns.
        Faster training and convergence due to pre-trained features.

    - Key Limitations:
        Requires higher computational resources.
        Slightly less flexible for customization compared to the custom model.

- **Summary :**
Custom Architecture is ideal for scenarios requiring lightweight models with fewer resources.
VGG16 is the better choice for achieving higher accuracy and handling complex datasets effectively.
