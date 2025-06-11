# Lesion Segmentation in Breast Ultrasound Images Using-U-Net and K-Means Methods
Breast cancer is one of the most common causes of death among women worldwide. Early detection helps in reducing the number of early deaths. The data reviews the medical images of breast cancer using ultrasound scans. The Breast Ultrasound Dataset is categorized into three classes: normal, benign, and malignant images. Breast ultrasound images can produce great results in classification, detection, and segmentation of breast cancer when combined with machine learning.

However, in this project, only benign segmentation is used to focus on identifying benign tumors and distinguishing them from normal and malignant tissues.

## Dataset
The Breast Ultrasound Images Dataset consists of data collected at baseline, which includes breast ultrasound images from women aged between 25 and 75 years old. The data was collected in 2018, with a total of 600 female patients. The dataset contains 780 images, each with an average size of 500x500 pixels in PNG format. The images are categorized into three classes: normal, benign, and malignant. The benign class specifically has 437 images and 454 masks. Ground truth images are provided along with the original images.
![image](https://github.com/user-attachments/assets/f859fb52-c458-4876-9627-4e3262753bb2)


## Methodology
In this project, two methods will be used for breast ultrasound image segmentation as a comparison: U-Net and K-Means.

U-Net: U-Net is a convolutional neural network architecture designed for medical image segmentation. It consists of an encoder-decoder structure with skip connections, allowing it to retain spatial information and accurately segment complex objects, such as tumors in breast ultrasound images.

K-Means: K-Means is a clustering algorithm that groups pixels in an image based on similarity. It divides the image into clusters, which can then be used to identify tumor regions. Although not specifically designed for segmentation, K-Means is a simple and effective method for image segmentation tasks.

These methods will be compared to evaluate the effectiveness of deep learning-based segmentation (U-Net) versus traditional clustering (K-Means) for detecting tumors in breast ultrasound images.

## U-Net Architecture
U-Net is a State of the Art CNN architecture for Bio-medical image segmentation. The architecture consists of a contracting path to capture context and a symmetric expanding path that enables precise localization. It's a Fully Convolutional Network(FCN) therefore it can work with arbitrary size images! I've implemented an architecture similar to the original U-Net architecture, except I've used "same" padding instead "valid" which the authors have used. Using "same" padding throughout makes the output segmentation mask of same (height, width) as that of the input.
![Unet_Architecture](https://github.com/user-attachments/assets/cba44a63-0845-4c87-bcef-89422cc4b0c0)

## Training
![image](https://github.com/user-attachments/assets/006d7a67-59f5-4a16-a796-bdfa60fe3f56)

## Result U-Net
![image](https://github.com/user-attachments/assets/e904c0bd-cd06-450f-a7b8-05f62e1e23b6)

## Comparison Result Between U-Net and K-Means
![image](https://github.com/user-attachments/assets/5d923643-de4e-40d0-b003-a8088f9d8705)

## Analysis and Conclusion
**1. Model Performance Evaluation**
| Metode      | Mean Accuracy | Mean IoU  | Dice Coefficient | Precision | Recall     | F1 Score |
| ----------- | ------------- | --------- | ---------------- | --------- | ---------- | -------- |
| **U-Net**   | **0.9660**    | **0.798** | **0.774**        | 0.796     | 0.753      | 0.774    |
| **K-Means** | 0.4724        | 0.0827    | 0.143            | 0.0894    | **0.7371** | 0.1429   |

The accuracy, IoU, and Dice Coefficient of U-Net are much higher than K-Means, indicating that U-Net is very superior in segmenting relevant lesion areas.

K-Means has a high recall (0.7371), which means that this method tends to capture many lesion areas, but with a very low precision (0.0894), indicating that most of the lesion predictions by K-Means are false positives (wrong segmentation).

The F1 Score of K-Means is also very low, reflecting a poor balance between precision and recall.

**2. Visualization and Prediction Quality**
U-Net provides clean, smooth, and ground truth segmentation, with IoU values ​​consistently above 0.8 in most cases.

K-Means produces very noisy segmentation, with predictions scattered and not resembling the shape of the original lesion.

On images with larger or more pronounced lesions, U-Net remains accurate, while K-Means does not show significant improvement.

**3. Learning Curve**
The loss and accuracy graphs show that the training and validation performance of U-Net is stable and improves with epochs.

The validation accuracy reaches more than 0.96, indicating that the model generalizes well to unseen data.

There is no significant overfitting, because the difference between training and validation is relatively small.

## Reference
[1]. Kemenkes RI. (2019). Hari Kanker Sedunia 2019. https://www.kemkes.go.id/article/view/19020100003/hari-kanker-sedunia2019.html.
[2]. Ciputra Medical Center (2024). Pemeriksaan USG Payudara. Retrieved from https://www.ciputramedicalcenter.com/pemeriksaan-usg-payudara/
[3]. Aggarwal, S., Garg, M., Kumar, · Ashok, & Kapila, · Rajat. (2024a). Discover Sustainability Breast lesions segmentation from ultrasound images using DeepLabV3 + model with channel and spatial attention mechanism. 5, 217. https://doi.org/10.1007/s43621-024-00424-x
[4]. Giaquinto, A. N., Sung, H., Miller, K. D., Kramer, J. L., Newman, L. A., Minihan, A., Jemal, A., & Siegel, R. L. (2022). Breast Cancer Statistics, 2022. CA: A Cancer Journal for Clinicians, 72(6), 524–541. https://doi.org/10.3322/caac.21754
[5]. Alhafiz, M. I., Wirasno, & Solichin, A. (2025).Segmentasi dengan metode active contour untuk peningkatan akurasi klasifikasi citra USG kanker payudara menggunakan K-Nearest Neighbor (KNN). JIPI (Jurnal Ilmiah Penelitian dan Pembelajaran Informatika), 10(1), 34–48. Diakses dari https://jurnal.stkippgritulungagung.ac.id/index.php/jipi/article/view/5681/2448
[6]. Alyafara, N. J. (2020). Studi tentang kanker payudara [Skripsi].  Universitas Islam Negeri Walisongo. Diakses dari.  https://eprints.walisongo.ac.id/id/eprint/12864/1/1508026012_Nelly%20J.%20Alya%20Fara_Full%20Skripsi%20-%20Nelly%20Alyafara.pdf
[7]. Kartika Sari, N. L., Iriani, R. D., & Santoso, B. (2020). Pengolahan citra untuk meningkatkan visualisasi lesi jinak citra USG payudara. Jurnal Ilmiah Giga, 23(2), 76–82. Diakses dari https://journal.unas.ac.id/giga/article/view/935
[8]. Guo Id, Y., Duan, X., Wang, C., & Guo, H. (2021). Segmentation and recognition of breast ultrasound images based on an expanded U-Net. https://doi.org/10.1371/journal.pone.0253202
[9]. Al-Dhabyani, W., Gomaa, M., Khaled, H., & Fahmy, A. (2020). Breast cancer segmentation using K-means clustering and optimized region-growing technique. Bulletin of Electrical Engineering and Informatics, 11(1), 158–167. doi: 10.11591/eei.v11i1.3458
[10]. Hesaraki, S., Mohammed, A. S., Eisaei, M., & Mousa, R. (2025). Breast cancer ultrasound image segmentation using improved 3DUnet++. WFUMB Ultrasound Open, 3(1), 100068. https://doi.org/10.1016/j.wfumbo.2024.100068
[11]. Lu, Y. (2025). Breast Ultrasound Image Segmentation Based on Attention U-Net. Proceedings of the 2nd International Conference on Machine Learning and Automation, CONF-MLA 2024, November 21, 2024, Adana, Turkey. https://doi.org/10.4108/eai.21-11-2024.2354629
[12]. Sulaiman, A., Anand, V., Gupta, S., Rajab, A., Alshahrani, H., Al Reshan, M. S., Shaikh, A., & Hamdi, M. (2024). Attention based UNet model for breast cancer segmentation using BUSI dataset. Scientific Reports 2024 14:1, 14(1), 1–13. https://doi.org/10.1038/s41598-024-72712-5
[13]. Zhao, T., & Dai, H. (2022). Breast Tumor Ultrasound Image Segmentation Method Based on Improved Residual U-Net Network. Computational Intelligence and Neuroscience, 2022(1), 3905998. https://doi.org/10.1155/2022/3905998
[14]. Abdulla, S. H., Sagheer, A. M., & Veisi, H. (2022). Breast cancer segmentation using K-means clustering and optimized region-growing technique. Bulletin of Electrical Engineering and Informatics, 11(1), 158–167. doi: 10.11591/eei.v11i1.3458












