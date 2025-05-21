# 🐶 Oxford IIIT Pet Dataset - Image Classification using PyTorch

This project demonstrates how to use PyTorch and torchvision to classify pet images from the [Oxford-IIIT Pet Dataset](https://www.robots.ox.ac.uk/~vgg/data/pets/) using a deep learning model (ReXNet) with transfer learning. It includes data visualization, class balancing insight, training monitoring, and model explainability with Grad-CAM.


---

## 📁 Dataset

We use the **Oxford-IIIT Pet Dataset**, which contains 37 categories (breeds of cats and dogs), with roughly 200 images for each class.

- ✅ Training Set  
- 🔍 Validation Set  
- 🧪 Test Set  

Data is split and preprocessed into PyTorch `DataLoader`s.
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



---
## 🧠 Model Architecture

We use **ReXNet v1.5**, a lightweight convolutional neural network optimized for efficiency and performance:

- **Backbone**: `rexnet_150` (loaded from `timm`)
- **Pretrained**: Yes (`imagenet`)
- **Final Layer**: Modified to match the number of pet classes (`num_classes=37`)
- **Loss**: `CrossEntropyLoss`
- **Metrics**: Accuracy and `F1Score` (`torchmetrics.F1Score` with `multiclass`)

---

## 🎯 Training Strategy

The training pipeline is built using a custom `TrainValidation` class:

- **Optimizer**: `Adam` with learning rate = `3e-4`
- **Scheduler**: `ReduceLROnPlateau` (monitors validation loss)
- **Early Stopping**: Stops training if F1-score doesn’t improve for 3 epochs
- **Epochs**: 25 (with early stopping)
- **Best Model Saving**: Based on highest F1-Score on validation set
- **Device**: GPU (`cuda`) or CPU fallback
- **Dev Mode**: For debugging small runs with `dev_mode=True`




---

## How to Run the Project

1. **Clone the Repository**
   ```bash
   git clone https://github.com/matrasulov/Oxford-IIIT-Pet-Dataset---Image-Classification-using-PyTorch.git
   cd Oxford-IIIT-Pet-Dataset---Image-Classification-using-PyTorch
