# Foreground-Preserving-DNN-Pipeline-for-Automated-CBC-from-Microscopic-Images
📌 Overview

This project presents a privacy-aware deep learning pipeline for automated Complete Blood Cell (CBC) counting from microscopic blood smear images. Unlike conventional approaches, it ensures that sensitive image data is never exposed to the model during training, while still achieving high segmentation and counting accuracy.

The system combines chaos-based encryption, task-aware biased decryption, U-Net-based segmentation, and classical image processing techniques to build a robust and interpretable pipeline.

🚀 Key Idea

Instead of feeding raw medical images into a neural network:

The image is encrypted using chaos-based methods
A biased decryption step reconstructs only the foreground (cells)
The model is trained only on this foreground-preserved representation

👉 This ensures:

🔒 Privacy preservation (background data is permanently destroyed)
🎯 Task-focused learning (model sees only relevant features)
🏗️ Pipeline Architecture
CLAHE Contrast Enhancement
Improves visibility under varying illumination and staining conditions
Foreground Mask Extraction (Otsu Thresholding)
Identifies cell regions
Chaos-Based Image Encryption
Logistic map-based permutation
XOR substitution for diffusion
Biased Decryption (Core Innovation)
Only foreground is reconstructed
Background remains encrypted
U-Net Based Multi-Head Segmentation
Foreground probability map
Boundary detection
Distance transform
Watershed Segmentation
Separates overlapping cells
Connected Component Analysis
Final cell counting (RBC, WBC, Platelets)
🧪 Results
Mask Dice Score: 0.8266
IoU: 0.7150
Cell Count MAE: 2.54
Counting Accuracy: ~61.4% (±2 cells)

🔐 Privacy Metrics:

NPCR: 99.50%
Entropy: 7.75 (near ideal randomness)
Low background reconstruction (strong privacy guarantee)
💡 Key Contributions
🔹 Biased Decryption Framework
First approach treating encryption as a learning-aware preprocessing step
🔹 Privacy-Preserving Training
Model never sees raw images
🔹 Hybrid Learning System
Combines deep learning + classical segmentation
🔹 Interpretable Pipeline
Deterministic counting via watershed + connected components
🛠️ Tech Stack
Python
PyTorch / TensorFlow
OpenCV, scikit-image
NumPy
📂 Dataset
Merged dataset from:
Complete Blood Cell Count Dataset
BCCD Dataset
Includes diverse conditions (lighting, staining, overlap)
📈 Applications
🏥 Automated hematology diagnostics
☁️ Privacy-safe cloud-based medical AI
📡 Telemedicine systems
🔬 Digital pathology
🔮 Future Work
Multi-class cell classification
Improved boundary-aware learning
Real-time deployment on edge devices
Adaptive encryption strategies
