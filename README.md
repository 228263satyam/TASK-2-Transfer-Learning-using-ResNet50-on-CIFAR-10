# Task 2 – Transfer Learning using ResNet50 on CIFAR-10

## 📌 Project Overview

This project implements **Transfer Learning using a pretrained ResNet50 model** for image classification on the **CIFAR-10 dataset**.

The experiment compares:

1. A **Custom CNN trained from scratch**
2. **ResNet50 with frozen pretrained layers**
3. **ResNet50 with selective fine-tuning of `layer4` and the final classifier**

The objective is to analyze the effect of transfer learning by comparing **accuracy, loss, training time, and trainable parameters**.

---

## 🎯 Objective

To implement transfer learning using a pretrained deep learning model and analyze its performance compared with a custom CNN architecture.

The project specifically demonstrates:

- Loading a pretrained ResNet50 model
- Using ImageNet pretrained weights
- Freezing the base layers
- Replacing the final classifier for CIFAR-10
- Fine-tuning selected deeper layers
- Comparing performance with a CNN trained from scratch
- Visualizing accuracy and loss
- Comparing training time and model parameters

---

## 📊 Dataset

### CIFAR-10

CIFAR-10 contains 10 image classes:

- Airplane
- Automobile
- Bird
- Cat
- Deer
- Dog
- Frog
- Horse
- Ship
- Truck

### Dataset Details

| Property | Value |
|---|---|
| Dataset | CIFAR-10 |
| Training Images | 50,000 |
| Test Images | 10,000 |
| Number of Classes | 10 |
| Original Image Size | 32 × 32 |
| Model Input Size | 96 × 96 |
| Normalization | ImageNet Mean/Std |

Training images are augmented using random horizontal flipping and random cropping.

---

## 🧠 Models Used

### 1. Custom CNN

A CNN is trained from scratch and used as the baseline model.

- Total parameters: **391,946**
- Trainable parameters: **391,946**
- Training epochs: **3**

### 2. ResNet50 – Frozen Base

A ResNet50 model pretrained on ImageNet is loaded.

The pretrained feature extractor is frozen and only the newly created 10-class classifier is trained.

- Total parameters: **23,528,522**
- Trainable parameters: **20,490**
- Training epochs: **2**

### 3. ResNet50 – Fine-Tuned

After the frozen-base stage, the ResNet50 `layer4` block and final classifier are made trainable.

- Total parameters: **23,528,522**
- Trainable parameters: **14,985,226**
- Fine-tuning epochs: **2**

---

## 📈 Experimental Results

| Model | Test Accuracy | Test Loss | Training Time |
|---|---:|---:|---:|
| Custom CNN | 64.93% | 1.0019 | 2.17 min |
| ResNet50 Frozen | 82.64% | 0.5150 | 1.56 min |
| ResNet50 Fine-Tuned | **92.79%** | **0.2173** | 3.47 min |

### Accuracy Improvement

The fine-tuned ResNet50 achieved:

**92.79% − 64.93% = +27.86 percentage points**

compared with the Custom CNN baseline.

The frozen ResNet50 already achieved an improvement of:

**82.64% − 64.93% = +17.71 percentage points**

over the Custom CNN.

---

## 📉 Visualizations

The notebook generates the following visualizations:

- Test Accuracy Comparison
- Test Loss Comparison
- Training Loss Comparison
- Final Test Accuracy Comparison
- Training Time Comparison
- Total vs Trainable Parameters
- Overall Performance Dashboard

---

## 🔬 Experimental Observations

- The Custom CNN achieved a final test accuracy of **64.93%**.
- The frozen pretrained ResNet50 achieved **82.64%**, showing that pretrained ImageNet features provide useful representations for the CIFAR-10 classification task.
- Fine-tuning `layer4` and the final classifier increased accuracy to **92.79%**.
- The fine-tuned model achieved the lowest recorded test loss of **0.2173**.
- The frozen ResNet50 required only **20,490 trainable parameters** during its initial transfer-learning stage.
- The complete transfer-learning pipeline took approximately **3.47 minutes** in the recorded run.

---

## 🛠️ Technologies Used

- Python
- PyTorch
- Torchvision
- NumPy
- Matplotlib
- Google Colab
- CIFAR-10
- ResNet50
- ImageNet pretrained weights

---

## 💻 Execution Environment

The supplied notebook was executed using:

- **Google Colab**
- **NVIDIA Tesla T4 GPU**
- CUDA-enabled PyTorch environment

---

## ▶️ How to Run

### Option 1 – Google Colab

1. Open the `.ipynb` file from this GitHub repository.
2. Click **Open in Colab** or upload the notebook to Google Colab.
3. Select a GPU runtime:
   - Runtime → Change runtime type → GPU
4. Run the notebook cells from top to bottom.
5. The CIFAR-10 dataset and pretrained ResNet50 weights will be downloaded automatically when required.

### Option 2 – Local Jupyter Notebook

Install the required libraries:

```bash
pip install torch torchvision numpy matplotlib
```

Then open:

```text
Task_2_Transfer_Learning_ResNet50_CIFAR10.ipynb
```

and run all cells.

---

## 📁 Repository Structure

```text
Task-2-Transfer-Learning/
│
├── Task_2_Transfer_Learning_ResNet50_CIFAR10.ipynb
├── README.md
│
└── task2_outputs/
    ├── accuracy_loss_comparison.png
    ├── accuracy_time_comparison.png
    ├── test_accuracy_comparison.png
    ├── test_loss_comparison.png
    ├── training_loss_comparison.png
    ├── final_accuracy_comparison.png
    ├── training_time_comparison.png
    ├── parameter_comparison.png
    ├── overall_performance_dashboard.png
    ├── sample_batch.png
    └── results.json
```

> The `task2_outputs` folder contains the generated experiment results and visualizations when these files are exported from the notebook.

---

## 📋 Assignment Requirements Covered

| Requirement | Status |
|---|---|
| Pretrained VGG16/ResNet model | ✅ ResNet50 |
| Freeze base layers | ✅ |
| Fine-tune selected layers | ✅ `layer4` + classifier |
| Retrain on custom dataset | ✅ CIFAR-10 |
| Baseline CNN comparison | ✅ |
| Accuracy comparison | ✅ |
| Loss visualization | ✅ |
| Training-time analysis | ✅ |
| Experimental observations | ✅ |
| Source code / Notebook | ✅ |
| Results and screenshots | ✅ |

---

## 👤 Author

**Satyam Yadav**

M.Sc. Data Science & Big Data Analyst

---

## 📌 Academic Note

This repository contains the implementation and measured experimental results for **Task 2: Transfer Learning using VGG16/ResNet**.

The final reported results are based on the recorded execution of the supplied notebook.

