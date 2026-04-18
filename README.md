# 🧬 Foreground-Aware Cryptographic Preprocessing for Cell Segmentation (CBC)

## 📌 Overview
This project proposes a **privacy-aware preprocessing pipeline** for medical image segmentation by combining **cryptographic transformations with deep learning**.

Instead of training directly on raw microscopy images, we introduce a **foreground-aware encryption and biased decryption mechanism** that:
- Preserves task-relevant regions (cells)
- Suppresses background noise
- Enhances robustness and feature learning

👉 Acts as a **hard attention prior + regularization mechanism** while maintaining **data privacy**

---

## 🚀 Key Idea

**Traditional pipeline:**
Raw Image → Deep Learning Model → Output

**Proposed pipeline:**
Raw Image → Foreground-aware Encryption → Biased Decryption → DNN → Output

---

## 🏗️ Architecture

Input Image  
↓  
CLAHE Enhancement  
↓  
Foreground Mask Generation  
↓  
Chaotic Encryption (Privacy Layer)  
↓  
Biased Decryption (Foreground Preservation)  
↓  
U-Net Segmentation  
↓  
Post-processing (Morphological Refinement)  

---

## 🧪 Features

- 🔐 Privacy-Preserving Training (raw data not directly exposed)
- 🎯 Foreground-Aware Representation
- 🧠 Inductive Bias via Cryptography
- 🔄 Plug-and-Play with standard CNNs (U-Net)

---

## 📊 Results

| Metric | Raw Input | Proposed Method |
|--------|----------|----------------|
| Dice Score | Lower | ~0.82 |
| IoU | Lower | ~0.71 |
| MAE (Counting) | Higher | Improved |

👉 Proposed method outperforms raw input under identical training conditions.

---

## 🔍 Ablation Study

Evaluated components:
- Raw images  
- CLAHE preprocessing  
- Mask-only input  
- Full encryption + decryption  
- **Biased decryption (proposed)**  

💡 Observation:  
Biased decryption provides gains beyond preprocessing and masking.

---

## 🔐 Security Metrics

- NPCR: High  
- Entropy: Near ideal  
- Correlation: Low  

---

## 📦 Tech Stack

- Python  
- PyTorch  
- OpenCV  
- NumPy / SciPy  

---

## ▶️ How to Run

```bash
git clone <repo-link>
cd project-folder
pip install -r requirements.txt
python train.py
