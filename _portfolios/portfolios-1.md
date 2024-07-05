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

<p align="center">
  Check out my <a href="https://github.com/PranayJagtap06/ML_Projects/tree/main/Hand_Signs_Classification">Hand Sign Classification project</a> on GitHub!
</p>

<figure style="text-align: center">
  <img src="/assets/img/model_tl_val_la.png" alt="Loss & Accuracy Curves" class="center-image" height="800px" widht="600px">
  <figcaption>Final Model Test set Loss & Accuracy Curves</figcaption>
</figure>

<figure style="text-align: center">
  <img src="/assets/img/model_tl_cm.png" alt="Confusion Matrix" class="center-image" height="600px" width="600px">
  <figcaption>Final Model Test set Confusion Matrix</figcaption>
</figure>

<p style="text-align: justify">
    This project is next-in-line to the Hand Sign Classification with CNN project. This project focuses on creating a strong image classification model that can identify six unique hand signs (0 to 5). The model uses the advantage of transfer learning with the EfficientNetB0 architecture to achieve high accuracy.
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
        <li> Test set loss: 28.21% </li> 
        <li> Test set accuracy: 93.33% </li> 
        <li> Test set Categorical Accuracy: 1.0 </li> 
        <li> Test set AUC-ROC score: 96.00% </li> 
        <li> Test set Classification Report: </li>
            <table>
                <thead>
                    <tr>
                    <th>hand signs</th>
                    <th>precision</th>
                    <th>recall</th>
                    <th>f1-score</th>
                    <th>support</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>hand sign 0</td>
                        <td>1.00</td>
                        <td>1.00</td>
                        <td>1.00</td>
                        <td>10</td>
                    </tr>
                    <tr>
                        <td>hand sign 1</td>
                        <td>0.90</td>
                        <td>0.90</td>
                        <td>0.90</td>
                        <td>10</td>
                    </tr>
                    <tr>
                        <td>hand sign 2</td>
                        <td>0.90</td>
                        <td>0.90</td>
                        <td>0.90</td>
                        <td>10</td>
                    </tr>
                    <tr>
                        <td>hand sign 3</td>
                        <td>1.00</td>
                        <td>1.00</td>
                        <td>1.00</td>
                        <td>10</td>
                    </tr>
                    <tr>
                        <td>hand sign 4</td>
                        <td>0.83</td>
                        <td>1.00</td>
                        <td>0.91</td>
                        <td>10</td>
                    </tr>
                    <tr>
                        <td>hand sign 5</td>
                        <td>1.00</td>
                        <td>0.80</td>
                        <td>0.89</td>
                        <td>10</td>
                    </tr>
                </tbody>
            </table>
    </ul>
    The classification report reveals high precision, recall, and F1-score across all hand sign classes, indicating the model's ability to accurately classify each category.<br><br>
    The final model's performance surpasses the previous CNN architecture base model by achieving 5% lower loss and 5% higher accuracy, along with a 3% higher AUC-ROC score. This significant improvement highlights the effectiveness of the transfer learning approach and the chosen model architecture.
</p>

**Conclusion**

<p style="text-align: justify">
    This project showcases my proficiency in building and training a high-performing transfer learning model for image classification. The proposed approach, utilizing EfficientNetB0 and a three-step fine-tuning strategy, effectively leverages pre-trained knowledge to achieve state-of-the-art results on the hand sign classification task. The model's impressive performance demonstrates the power of transfer learning in accelerating the development of accurate and efficient image recognition systems. 
</p>