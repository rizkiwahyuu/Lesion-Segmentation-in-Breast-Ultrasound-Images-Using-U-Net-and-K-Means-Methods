# Lesion-Segmentation-in-Breast-Ultrasound-Images-Using-U-Net-and-K-Means-Methods
Introduction
Triple Negative Breast Cancer
U-Net
Dataset
Results
Model's prediction comparision on different datasets
Activation Maps
Getting Started
Requirements
Installation
Dataset Directory Structure
Deployments
References





About Dataset
Breast cancer is one of the most common causes of death among women worldwide. Early detection helps in reducing the number of early deaths. The data reviews the medical images of breast cancer using ultrasound scan. Breast Ultrasound Dataset is categorized into three classes 
:
 normal, benign, and malignant images. Breast ultrasound images can produce great results in classification, detection, and segmentation of breast cancer when combined with machine learning.

The data collected at baseline include breast ultrasound images among women in ages between 25 and 75 years old. This data was collected in 2018. The number of patients is 600 female patients. The dataset consists of 780 images with an average image size of 500*500 pixels. The images are in PNG format. The ground truth images are presented with original images. The images are categorized into three classes, which are normal, benign, and malignant.

What is U-Net?
U-Net is a popular deep-learning architecture for semantic segmentation. Originally developed for medical images, it had great success in this field. But, that was only the beginning! From satellite images to handwritten characters, the architecture has improved performance on a range of data types.
The U-Net architecture has been widely used in various medical image segmentation tasks, such as brain tumor segmentation, lung segmentation, and cell segmentation, among others.
U-Net: Convolutional Networks for Biomedical Image Segmentation

![Unet_Architecture](https://github.com/user-attachments/assets/8112365c-56ce-48be-822a-7b43c6919fa0)

U-net architecture (example for 32x32 pixels in the lowest resolution). Each blue box corresponds to a multi-channel feature map. The number of channels is denoted on top of the box. The x-y-size is provided at the lower left edge of the box. White boxes represent copied feature maps. The arrows denote the different operations.

This illustration is an example of Unet architecture but layers can have different size.

We apply it for breast cancer image segmentation with some modifications to the model.
