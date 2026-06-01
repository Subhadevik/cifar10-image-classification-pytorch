# 🖼️ CIFAR-10 Image Classification using PyTorch

A custom Convolutional Neural Network (CNN) built from scratch using PyTorch to classify images from the CIFAR-10 dataset into 10 categories.

---

## 📌 Project Overview

CIFAR-10 is a well-known benchmark dataset containing **60,000 color images** (32×32 pixels) across **10 classes**:

> ✈️ Airplane | 🚗 Automobile | 🐦 Bird | 🐱 Cat | 🦌 Deer | 🐶 Dog | 🐸 Frog | 🐴 Horse | 🚢 Ship | 🚚 Truck

---

## 🏗️ Model Architecture

A 3-block custom CNN with the following structure:

```
Input (3×32×32)
    ↓
Block 1: Conv2d(3→32) → BatchNorm → ReLU → Conv2d(32→32) → BatchNorm → ReLU → MaxPool → Dropout(0.25)
    ↓
Block 2: Conv2d(32→64) → BatchNorm → ReLU → Conv2d(64→64) → BatchNorm → ReLU → MaxPool → Dropout(0.25)
    ↓
Block 3: Conv2d(64→128) → BatchNorm → ReLU → MaxPool → Dropout(0.25)
    ↓
Classifier: Linear(2048→512) → ReLU → Dropout(0.5) → Linear(512→10)
    ↓
Output (10 classes)
```

---

## ⚙️ Training Configuration

| Parameter | Value |
|---|---|
| Optimizer | Adam (lr=0.001, weight_decay=1e-4) |
| Loss Function | CrossEntropyLoss |
| Scheduler | StepLR (step=10, gamma=0.5) |
| Epochs | 20 |
| Batch Size | 64 |
| Device | GPU (CUDA) / CPU |

---

## 🔧 Data Augmentation

- Random Horizontal Flip
- Random Crop (32×32 with padding=4)
- Normalization (mean & std per channel)

---

## 📊 Results

| Metric | Value |
|---|---|
| Test Accuracy | 82.58% |
| Total Parameters | ~1.2M |

### Per-Class Accuracy

| Class | Accuracy |
|---|---|
| ✈️ Airplane | 80.00% |
| 🚗 Automobile | 90.60% |
| 🐦 Bird | 66.80% |
| 🐱 Cat | 54.00% |
| 🦌 Deer | 83.70% |
| 🐶 Dog | 80.10% |
| 🐸 Frog | 94.90% |
| 🐴 Horse | 86.90% |
| 🚢 Ship | 96.20% |
| 🚚 Truck | 92.60% |

---

## 🚀 How to Run

### Option 1: Google Colab (Recommended)
1. Open `cifar10_classification.ipynb` in Google Colab
2. Set Runtime → Change runtime type → **GPU (T4)**
3. Run all cells — dataset downloads automatically!

### Option 2: Local
```bash
git clone https://github.com/yourusername/cifar10-image-classification-pytorch.git
cd cifar10-image-classification-pytorch
pip install torch torchvision matplotlib numpy
jupyter notebook cifar10_classification.ipynb
```

---

## 📁 Project Structure

```
cifar10-image-classification-pytorch/
│
├── cifar10_classification.ipynb   # Main notebook
├── training_curves.png            # Loss & accuracy plots
├── cifar10_cnn.pth                # Saved model weights
└── README.md
```

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.10-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-2.x-orange)
![Torchvision](https://img.shields.io/badge/Torchvision-0.15-green)

- Python 3.10+
- PyTorch
- Torchvision
- Matplotlib
- NumPy

---

## 👩‍💻 Author

**Subhadevi Krishnaraj**  
AI & Data Science | IIT Madras Research Intern  
[LinkedIn](https://www.linkedin.com/in/subhadevi-krishnaraj) | [GitHub](https://github.com/Subhadevik)
