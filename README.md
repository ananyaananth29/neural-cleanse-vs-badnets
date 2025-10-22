# Neural Cleanse vs BadNets – Backdoor Attack and Defense on MNIST

This repository contains my implementation of **BadNets** and **Neural Cleanse** for the **CS 6958 / CS 4960 – Machine Learning Security (Fall 2025)** course assignment.  
The project explores both the creation and detection of **backdoor attacks** in neural networks using the **MNIST dataset**.

---

## 🧩 Project Overview

The project demonstrates two key concepts in machine learning security:

1. **Backdoor Attack (BadNets)**
   - Injects a small white 3×3 trigger patch into training images.
   - Forces the model to misclassify any image containing the trigger as a specific target label (label `0`).
   - Evaluates the model’s performance on both clean and poisoned datasets.

2. **Backdoor Detection (Neural Cleanse)**
   - Implements a defense strategy that reverse-engineers potential triggers for each output class.
   - Uses **mask** and **pattern** optimization guided by cross-entropy loss and L1 regularization.
   - Applies **Median Absolute Deviation (MAD)** analysis to detect anomalous (potentially backdoored) target classes.

---

## ⚙️ Implementation Details

- **Framework:** PyTorch  
- **Dataset:** MNIST (handwritten digits)  
- **Attack model:** CNN trained on 10% poisoned data  
- **Defense model:** Neural Cleanse using trigger reverse-engineering  

### Directory Structure
├── HW2.ipynb # Jupyter notebook with full implementation
├── homework2.docx # Assignment description
├── /models # Saved model weights during training
└── /data # MNIST dataset (auto-downloaded by PyTorch)
---

## 🚀 Results Summary

| Metric | Description | Result |
|--------|--------------|--------|
| **Clean Accuracy** | Accuracy on unpoisoned test set | 0.9901 |
| **Attack Success Rate (ASR)** | % of triggered images classified as target | 1.0000 |
| **Neural Cleanse Detection** | Detected anomalous class via MAD analysis | **Class 2 flagged (true target was 0)** |
| **Interpretation** | Neural Cleanse correctly identified the model as backdoored, though with slight target mismatch due to small trigger and fixed λ. |

---

## 🖼️ Visualization

**Example: BadNets attack**

![output](https://github.com/ananyaananth29/neural-cleanse-vs-badnets/blob/main/output.png)

---

## 🧠 Key Learnings

- Backdoor attacks like **BadNets** can stealthily compromise a model’s predictions with minimal visual changes.
- **Neural Cleanse** is effective in detecting anomalous backdoor patterns using statistical outlier analysis.
- Small triggers and fixed hyperparameters may lead to near-target anomalies rather than exact label detection.

---

## 📚 References

- **BadNets:** Gu et al., *BadNets: Identifying Vulnerabilities in the Machine Learning Model Supply Chain* (2017).  
- **Neural Cleanse:** Wang et al., *Neural Cleanse: Identifying and Mitigating Backdoor Attacks in Neural Networks* (IEEE S&P 2019).

---

## 🧑‍💻 Author
**Ananya Ananth**  
Graduate Student – Machine Learning Security  
University of Utah 
Course: CS 6958 / CS 4960 – Fall 2025  
