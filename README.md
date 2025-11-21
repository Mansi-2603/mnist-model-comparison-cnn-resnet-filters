# mnist-model-comparison-cnn-resnet-filters
A comprehensive comparison of deep learning models on MNIST, evaluating a Basic CNN, a ResNet-like architecture, and a CNN trained on manually filtered images (Sobel, Laplacian, Blur, Sharpen, Custom kernels). Includes accuracy benchmarking, confusion matrices, and grouped bar-chart visualizations

This project explores different deep learning and classical image-processing approaches for handwritten digit classification using the MNIST dataset.  
The goal was to compare the performance of:

1. **A baseline Convolutional Neural Network (CNN)**
2. **A custom ResNet-like architecture**
3. **The CNN evaluated on MNIST images transformed using classical filters**
   - Sobel (vertical/horizontal edges)
   - Laplacian
   - Gaussian blur
   - Sharpening kernel
   - Walsh-like diagonal filter
   - Box blur

---

## 📊 Model Architectures

### **1️⃣ Basic CNN**
- 2 convolution blocks  
- MaxPooling + ReLU  
- Dense classifier  
- ~0.985 accuracy  

### **2️⃣ ResNet-like Model**
- Residual skip connections  
- Batch Normalization  
- Deeper feature extraction  
- ~0.993–0.995 accuracy (best performance)  

### **3️⃣ Filtered Images + CNN**
Each MNIST test image was pre-processed using classical 3×3 kernels.  
These filtered images were fed into the trained CNN to measure robustness.

---

## 🧪 Results Summary

| Model / Processing Method | Accuracy |
|--------------------------|----------|
| **Basic CNN** | ~0.985 |
| **ResNet-like Model** | **0.993–0.995** |
| **CNN on Sharpened Images** | ~0.95 |
| **CNN on Sobel Vertical** | ~0.94 |
| **CNN on Sobel Horizontal** | ~0.93 |
| **CNN on Gaussian Blur** | ~0.92 |
| **CNN on Box Blur** | ~0.91 |
| **CNN on Laplacian Filter** | ~0.87 |

---

## 🎨 Visual Comparison

A side-by-side grouped bar chart was generated to compare:

- Baseline CNN  
- ResNet-like model  
- All filtered-image accuracies  

This visualization clearly shows the performance degradation caused by blur and Laplacian filters, while edge-detection filters preserve reasonable classification performance.

---

## 📝 Key Insights

- **ResNet-like architecture is the most accurate**, thanks to skip connections that allow deeper learning without vanishing gradients.
- **Classical filters significantly affect accuracy**:
  - Edge-detection filters keep digit structure → moderate accuracy.
  - Blurring reduces key features → noticeable accuracy drop.
  - Laplacian introduces noise → lowest performance.
- **Deep networks are sensitive to input transformations**, demonstrating the importance of robust preprocessing in real-world applications.

---

## 📂 Project Structure

