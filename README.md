# 🖊️ MNIST Digit Classifier Using PyTorch

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/) 
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0-orange)](https://pytorch.org/) 
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

---

## 📌 Project Overview
This project implements a **fully connected neural network (MLP)** to classify handwritten digits from the **MNIST dataset** using **PyTorch**.  

- **Training set:** 60,000 images  
- **Test set:** 10,000 images  
- **Input:** 28×28 grayscale images  
- **Output:** Predicted digit (0–9)  

The model achieves **~97–98% test accuracy** on MNIST after training for **5 epochs**.

---

## 🛠️ Features
- Feedforward neural network with **2 hidden layers** (128 → 64 neurons).  
- **ReLU activation** for non-linearity.  
- **CrossEntropyLoss** for classification.  
- Fully compatible with **GPU/CPU**.  
- Automatic **dataset download** via `torchvision.datasets`.  
- **Visualizes** test images along with actual and predicted labels.  
- Saves trained model as `mnist_model.pth`.

---

## ⚡ How It Works
1. **Data Loading:**  
   - MNIST dataset is downloaded if not present.  
   - Images are converted to tensors using `transforms.ToTensor()`.  
   - Data is batched using `DataLoader` (batch size = 64).  

2. **Model Architecture:**  
   - Input: 28×28 = 784 features → Hidden Layer 1: 128 → Hidden Layer 2: 64 → Output: 10 classes  
   - Activation: `ReLU`  
   - Optimizer: `Adam` (learning rate = 0.001)  

3. **Training Loop:**  
   - Runs for **5 epochs**.  
   - Calculates and prints **total loss per epoch**.  
   - Updates weights using backpropagation.  

4. **Evaluation:**  
   - Computes predictions with `argmax` on output logits.  
   - Calculates total accuracy on **10,000 test images**.  

5. **Visualization & Prediction:**  
   - Displays a sample test image.  
   - Shows **actual vs predicted label**.  

---

## 📊 Example Output
- **Test Accuracy:** `97.58%`  
- **Sample Prediction:**  

| Index | Actual | Predicted |
|-------|--------|-----------|
| 100   | 7      | 7         |  

---

## 🚀 How to Run in Google Colab
1. Open [Google Colab](https://colab.research.google.com/).  
2. Upload your Python script or paste code in a new notebook.  
3. Install dependencies:

```python
!pip install torch torchvision matplotlib
