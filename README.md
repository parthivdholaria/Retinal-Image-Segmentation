### README: Retinal Vessel Image Segmentation

---

#### **Overview**

This project focuses on the segmentation of blood vessels in retinal images, which plays a critical role in diagnosing and monitoring various ophthalmological and cardiovascular diseases. The segmentation process involves identifying and isolating retinal vessel structures to facilitate early diagnosis and better treatment planning for conditions like diabetic retinopathy and glaucoma.

---

#### **Dataset**

- **Dataset Name**: CHASEDB1
- **Description**:
  - Consists of 28 retinal images, representing both eyes (left and right) of 14 participants.
  - Each image is accompanied by two ground-truth annotations provided by different human observers.
  - Images have a resolution of 2,688,000 pixels.
- **File Naming Convention**:
  - Participant numbers: `01–14`
  - Eye identifiers: `L (Left)` or `R (Right)`
  - Ground truth sources: `1stHO` or `2ndHO`

---

#### **Objectives**

1. Develop a robust system for the segmentation of blood vessels in retinal images.
2. Analyze and enhance various preprocessing and augmentation techniques for improving segmentation performance.

---

#### **Techniques and Methodology**

1. **Preprocessing Techniques**:
   - Green channel isolation for better vessel contrast.
   - Random brightness scaling to simulate various lighting conditions.
   - CLAHE (Contrast-Limited Adaptive Histogram Equalization) for local contrast enhancement.
   - Gaussian noise addition for robustness testing.

2. **Segmentation Pipeline**:
   - Morphological operations for structure enhancement.
   - Hessian matrix and eigenvalue transformations for highlighting wide and thin vessels.
   - Otsu’s Thresholding to separate vessels from the background.

3. **Model Used**:
   - **U-Net**: A convolutional neural network with encoder-decoder architecture designed for image segmentation. The model leverages skip connections to retain spatial details.

---

#### **Results**

| **Dataset**              | **Accuracy** | **Sensitivity** | **Specificity** | **F1 Score** | **SSIM** | **PSNR** |
|--------------------------|--------------|-----------------|-----------------|--------------|----------|----------|
| Original Dataset         | 0.9634       | 0.6191          | 0.9903          | 0.7543       | 0.8721   | 62.5135  |
| Scaled Dataset (50%)     | 0.9678       | 0.6643          | 0.9901          | 0.8354       | 0.8743   | 62.8732  |
| Scaled Dataset (100%)    | **0.9703**   | **0.7647**      | 0.9869          | **0.8614**   | **0.8884** | **63.4093** |

Key Findings:
- Scaling improved segmentation metrics such as accuracy, sensitivity, and F1 Score.
- CLAHE and random Gaussian noise yielded mixed results, requiring further fine-tuning.

---

#### **Conclusion**

- Green channel isolation combined with random brightness scaling and CLAHE enhances segmentation performance.
- U-Net demonstrates high accuracy and robustness when applied to scaled datasets.

---

#### **Future Work**

- Explore additional augmentation techniques and advanced architectures.
- Evaluate performance on real-world clinical datasets.
- Test scalability with larger and more diverse retinal image datasets.

---

#### **Code Availability**

- **GitHub Repository**: [Retinal Image Segmentation](https://github.com/parthivdholaria/Retinal-Image-Segmentation/tree/main)
- **Dataset**: [CHASEDB1 on Kaggle](https://www.kaggle.com/datasets/khoongweihao/chasedb1)

---

#### **Authors**
- **Utsav Garg (2021108)**
- **Parthiv Dholaria (2021078)**
