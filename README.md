# mnist-model-comparison-cnn-resnet-filters
A comprehensive comparison of deep learning models on MNIST, evaluating a Basic CNN, a ResNet-like architecture, and a CNN trained on manually filtered images (Sobel, Laplacian, Blur, Sharpen, Custom kernels). Includes accuracy benchmarking, confusion matrices, and grouped bar-chart visualizations
# Performance Comparison: CNN vs ResNet vs Filtered Images (MNIST)

This project explores how different feature extraction techniques affect image classification performance on the **MNIST handwritten digits dataset**.  
It compares:

- **A Basic CNN model**
- **A ResNet-like model built from custom residual blocks**
- **Classical handcrafted image filters** (Sobel, Laplacian, Gaussian Blur, Sharpen, etc.)

The goal is to analyze how modern deep learning models perform relative to traditional image preprocessing methods, and how each technique impacts accuracy.

---

## 📌 Project Overview

This project performs a detailed comparison between three different approaches:

### **1️⃣ Basic CNN**
A sequential Convolutional Neural Network consisting of:
- Conv2D + BatchNorm + ReLU
- MaxPooling + Dropout
- Dense layers  
This acts as the baseline.

### **2️⃣ ResNet-like Model**
A custom-built residual neural network:
- Uses manually implemented **residual blocks**
- Skip connections improve gradient flow
- Faster convergence than the CNN

### **3️⃣ Classical Image Filters**
Before classification, test images are transformed using 7 handcrafted kernels:

| Filter Name | Description |
|------------|-------------|
| Sharpen | Highlights edges and intensifies structure |
| Blur | Smoothens the image |
| Vertical Edge | Sobel operator (vertical) |
| Horizontal Edge | Sobel operator (horizontal) |
| Gaussian Blur | Smooths noise with weighted blur |
| Laplacian | Second-order derivative edge detection |
| Walsh-like | Diagonal contrast-sensitive pattern |

Each filtered dataset is evaluated using the **trained CNN**.

---

## 📊 Results Summary

### **Model Accuracies**
| Model | Test Accuracy |
|-------|----------------|
| **Basic CNN** | ~0.99 |
| **ResNet-like Model** | ~0.99+ |
| **Filtered Images (Average)** | ~0.80–0.92 depending on filter |

ResNet shows **faster convergence and slightly better accuracy**, while filters show significant variation depending on their feature extraction capability.

---

## 📈 Visualizations

### ✔️ Accuracy vs Epochs (CNN vs ResNet)
Shows how quickly both models converge.

### ✔️ Loss vs Epochs (CNN vs ResNet)
ResNet stabilizes faster due to skip connections.

### ✔️ Bar Chart: CNN vs ResNet vs All Filters
Displays per-filter performance compared to learned models.

All plots are generated using Matplotlib.

---

## 📦 Technologies Used

- **TensorFlow / Keras**
- **NumPy**
- **Matplotlib**
- **SciPy (convolution2d)**
- **MNIST Dataset**

---

## 🧠 How Residual Blocks Help

Residual connections allow:

- Better gradient flow  
- Reduced vanishing gradient problem  
- Faster convergence  
- Better generalization  

This is why even a small ResNet-like model outperforms the basic CNN.

---

## 🧪 Filters Used in This Project

Each filter is applied to the MNIST test set using 2D convolution:

```python
convolve2d(image, kernel, mode="same", boundary="fill")


---

## 📂 Project Structure

