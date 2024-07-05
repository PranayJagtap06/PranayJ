---
layout: portfolio
title: "Fine Tuned Hand Sign Classifier"
subtitle: "0-5 hand sings classification using Transfer Learning"
cover-img: /assets/img/ml_img.jpg
thumbnail-img: /assets/img/model_tl_cm.png
share-img: /assets/img/ml_img.jpg
date: 2024-07-02
author: Pranay Jagtap
---

**Hand Sign Classification using Transfer Learning**

<p style="text-align: justify">
    This project works to create a strong image classification model that can identify six unique hand signs (0 to 5). The model uses the advantage of transfer learning with the EfficientNetB0 architecture to achieve high accuracy 
</p>

**Data Prepsocessing**

<p style="text-align: justify">
    The image dataset went through detailed preparation to boost model function. Images were adjusted to a set size of (224, 224, 3) to meet the input needs of the EfficientNetB0 model. Normalization was left out since the EfficientNetB0 design includes a built-in normalization layer making the preparation process simpler.
</p>

**Model Architecture & Training**

<p style="text-align: justify">
    The model architecture was carefully crafted using the Keras Functional API, with EfficientNetB0 serving as the base model.
    The model architecture consists of:
    <ul> 
        <li> <i> An input layer receiving images of size (224, 224, 3). </i> </li> 
        <li> <i> A data augmentation layer for data augmentation. </i> </li> 
        <li> <i> The pre-trained EfficientNetB0 model serving as the feature extractor. </i> </li> 
        <li> <i> A global average pooling layer to reduce the spatial dimensions of the feature maps. </i> </li> 
        <li> <i> A dense output layer with 6 neurons, one for each hand sign class, with softmax activation. </i> </li> 
    </ul><br>
    A strategic three-step approach was employed for model building and training:
    <ul>
        <li> <b> Base Model Development: </b> <i> First, a base model was built to include a data augmentation layer and EfficientNetB0. This model was taught using 10% of the training data to implement feature extraction transfer learning. </i> </li>
        <li> <b> Fine-Tuning: </b> <i> The base model went through fine-tuning by making the top 10 layers of EfficientNetB0 trainable and reducing the learning rate by 10%. This process was done on 10% of the training data. </i> </li>
        <li> <b> Full Dataset Training: </b> <i> At last, the optimized model now fine-tuned, was trained using 100% of the training data to improve performance. </i> </li>
    </ul>
</p>

**Model Evaluation & Performance**

<p style="text-align: justify">
    The trained model demonstrates impressive performance on the test set, achieving: 
    <ul> 
        <li> Test set loss: 28.21%</li> 
        <li> Test set accuracy: 93.33%</li> 
        <li> Test set Categorical Accuracy: 1.0</li> 
        <li> Test set AUC-ROC score: 96.00%</li> 
    </ul>
    The classification report reveals high precision, recall, and F1-score across all hand sign classes, indicating the model's ability to accurately classify each category.<br><br>
    The final model's performance surpasses the previous CNN architecture base model by achieving 5% lower loss and 5% higher accuracy, along with a 3% higher AUC-ROC score. This significant improvement highlights the effectiveness of the transfer learning approach and the chosen model architecture.
</p>

Test set Classification Report:
| hand signs | precision | recall | f1-scre | support |
| ---- | ---- | ---- | ---- | ---- |
| hand sign 0 | 1.00 | 1.00 | 1.00 | 10 |
| hand sign 1 | 0.90 | 0.90 | 0.90 | 10 |
| hand sign 2 | 0.90 | 0.90 | 0.90 | 10 |
| hand sign 3 | 1.00 | 1.00 | 1.00 | 10 |
| hand sign 4 | 0.83 | 1.00 | 0.91 | 10 |
| hand sign 5 | 1.00 | 0.80 | 0.89 | 10 |

**Conclusion**

<p style="text-align: justify">
    This project showcases my proficiency in building and training a high-performing transfer learning model for image classification. The proposed approach, utilizing EfficientNetB0 and a three-step fine-tuning strategy, effectively leverages pre-trained knowledge to achieve state-of-the-art results on the hand sign classification task. The model's impressive performance demonstrates the power of transfer learning in accelerating the development of accurate and efficient image recognition systems. 
</p>