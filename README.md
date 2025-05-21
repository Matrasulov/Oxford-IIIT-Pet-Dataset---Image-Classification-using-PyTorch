# 🐶 Oxford IIIT Pet Dataset - Image Classification using PyTorch

This project demonstrates how to use PyTorch and torchvision to classify pet images from the [Oxford-IIIT Pet Dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/). The notebook walks through data loading, model creation, training, and evaluation.

---

## 📁 Dataset

- **Dataset**: Oxford-IIIT Pet Dataset (loaded using `torchvision.datasets.OxfordIIITPet`)
- **Classes**: 37 pet breeds
- **Format**: Images and segmentation masks

---

---

## What the Notebook Covers

1. **Data Loading & Preprocessing**  
   - Loading the dataset using `torchvision.datasets.OxfordIIITPet`.
   - Applying necessary transformations (resizing, normalization, etc.).

2. **Data Visualization**  
- ✅ **Random Samples from Dataset** – to understand image formats and contents.
  
  ![gt_plot](https://github.com/user-attachments/assets/2d8525f2-d00f-420e-b04c-87a9822ca1c8)

---
- ⚖️ **Class Distribution Charts** – visualize imbalance across train, validation, and test sets.

![tr_cls_imbalance](https://github.com/user-attachments/assets/e4c46aeb-1ba2-481c-87d1-fc209428aebe)

---
![val_cls_imbalance](https://github.com/user-attachments/assets/2e937401-ad04-4d70-96fb-b504c8d5f25f)

---
![ts_ds_class_imbalance](https://github.com/user-attachments/assets/ccb67355-31c3-405a-b54c-02468cbc0259)

---

- 📉 **Training and Validation Accuracy Curves** – to monitor learning progress.
  ![acc_score](https://github.com/user-attachments/assets/44238ef6-74c3-4036-a9ff-3c9992dbc11e)

  ---
  - 🔍 **Grad-CAM Heatmaps** - to interpret what regions of the image the model is focusing on.
    ![grad_cam_plus](https://github.com/user-attachments/assets/fb366824-660d-46df-b960-30339a9771bd)

    ---
    - 🔀 **Confusion Matrix** – to evaluate class-wise performance.
      ![confusion matrix](https://github.com/user-attachments/assets/ed801bec-05a6-4065-9a0e-3b78e4d2f4d4)



3. **Model Definition & Training**  
   - Building a CNN (or using a pre-trained model) for image classification.
   - Training the model on the dataset.

4. **Evaluation**  
   - Evaluating model performance with metrics and visualizations (loss curves, accuracy, etc.).

---

## How to Run the Project

1. **Clone the Repository**
   ```bash
   git clone https://github.com/matrasulov/Oxford-IIIT-Pet-Dataset---Image-Classification-using-PyTorch.git
   cd Oxford-IIIT-Pet-Dataset---Image-Classification-using-PyTorch
