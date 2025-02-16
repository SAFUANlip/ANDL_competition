# Competition Results & Methodologies  

This repository contains our solutions and findings from two machine learning competitions:  
1. **Blood Cell Classification** (Supervised classification of microscopic blood cell images)  
2. **Mars Terrain Segmentation** (Semantic segmentation of Martian surface types)  

---  

## 🩸 Blood Cell Classification – Competition Overview  
**Final Ranking Position: 100 / 200**  

### Introduction  
The goal of this competition was to classify **microscopic blood cell images** into **8 distinct classes** using supervised learning techniques.  

### Dataset  
- **13,759** RGB images (96×96 pixels, 3 channels).  

### Key Findings  

- **Best Model Performance:**  
  - Our best model was an **ensemble of two top-performing models**, leading to an **8% accuracy increase** (**from 62% to 70%**).  
  - This improvement was due to the **diverse features learned** by different architectures. Shallower models capture **generalized features**, while deeper models focus on **more semantic features**, making them complementary.  

- **Data Augmentation:**  
  - **Simple augmentations** improved model performance.  
  - **Complex augmentations** often led to performance degradation.  

- **Transfer Learning & Fine-Tuning:**  
  - Using **pre-trained models with transfer learning** resulted in a **20% accuracy boost** (**from 42% to 62%**).  
  - However, **fine-tuning large models** often led to **marginal improvements** or even **overfitting** due to the small dataset size.  

- **Model Complexity vs. Performance:**  
  - **More parameters did not always mean better performance.**  
  - **MobileNetV2 (2M parameters)** outperformed **ConvNeXtBase (87M parameters) by 21%**.  
  - Increasing model size sometimes helped, e.g., transitioning from **EfficientNetB2 (8M parameters) to EfficientNetV2s (20M parameters)** resulted in a **20% performance boost**.  
  - However, no noticeable gains were observed when comparing **MobileNetV2 (2M parameters) to MobileNetV3Large (3M parameters)**.  

---

## 🪐 Mars Terrain Segmentation – Competition Overview  
**Final Ranking Position: 19 / 197**  

### Introduction  
This competition involved **semantic segmentation of Martian terrain** into **five distinct surface classes** using grayscale images.  

### Dataset  
- **2,615** grayscale training images (64×128 pixels) with corresponding segmentation masks.  
- **10,022** test images (64×128 pixels) without labels.  

#### Challenges:  
- **Significant class imbalance**  
- **Inconsistent labeling** (due to multiple annotators and the complexity of Martian terrain)  

### Key Findings  

- **Best Model Performance:**  
  - An **ensemble of four top-performing models** improved **mIoU from 66.0% to 68.4%** (+2.4%).  

- **Class Imbalance Mitigation:**  
  - **Simple image duplication** for the least represented class improved U-Net model performance by **9%**.  
  - Among **various loss functions tested**, only **Focal Loss (γ = 2)** provided balanced results.  

- **Impact of Background Class:**  
  - Including the **background class in loss computation** caused the model to neglect other classes, dropping performance by **more than 10%**.  

- **Data Augmentation & Overfitting:**  
  - Augmentations **slightly improved** performance but were most effective when combined with **class duplication**.  
  - **Duplicating all images** led to **overfitting**, reducing performance by **10%** compared to our best model.  

- **Model Comparisons:**  
  - **U-Net and U-Net++ (MobileNetV2 encoder)** outperformed more recent architectures like **DeepLabV3Plus, SegFormer, PSPNet, and FPN**.  

---

## 📂 Repository Structure  

- 📂 [BloodCells](BloodCells/)  
  - 📂 [notebooks](BloodCells/notebooks/)  
  - 📄 [BloodCellsDreamTeamReport.pdf](BloodCells/BloodCellsDreamTeamReport.pdf)  

- 📂 [Mars](Mars/)  
  - 📂 [notebooks](Mars/notebooks/)  
  - 📄 [MarsDreamTeamReport.pdf](Mars/MarsDreamTeamReport.pdf)  

---

## Team Members

* Alisa Pesotskaia
* Iusupov Safuan [Telegram](https://t.me/IusupovSafuan) | [GitHub](https://github.com/SAFUANlip) | safuan.iusupov@mail.polimi.it
* Davide Paltrinieri
* Dario Napolitano [GitHub](https://github.com/Darionapo2) | dario2.napolitano@mail.polimi.it
