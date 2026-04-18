# Foreground-Preserving-DNN-Pipeline-for-Automated-CBC-from-Microscopic-Images
📌 Overview

This project proposes a novel privacy-aware preprocessing pipeline for medical image segmentation by combining cryptographic transformations with deep learning.

Instead of training directly on raw microscopy images, we introduce a foreground-aware encryption and biased decryption mechanism that:

Preserves task-relevant regions (cells)
Suppresses background noise
Enhances robustness and feature learning

👉 The system effectively acts as a hard attention prior + regularization mechanism while maintaining data privacy.

🚀 Key Idea

Traditional pipeline:

Raw Image → Deep Learning Model → Output

Proposed pipeline:

Raw Image → Foreground-aware Encryption → Biased Decryption → DNN → Output
🔑 Core Insight

Controlled information suppression via biased decryption improves learning by enforcing task-specific inductive bias.

🏗️ Architecture
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
🧪 Features
🔐 Privacy-Preserving Training
Raw data is never directly exposed to the model
🎯 Foreground-Aware Representation
Background suppression improves segmentation focus
🧠 Inductive Bias via Cryptography
Acts similar to attention but enforced at input level
🔄 Plug-and-Play
Compatible with standard CNN architectures (U-Net)
📊 Results
Metric	Raw Input	Proposed Method
Dice Score	↓	↑ ~0.82
IoU	↓	↑ ~0.71
MAE (Counting)	↓	Improved

👉 The proposed method consistently outperforms raw input under identical training conditions.

🔍 Ablation Study

We evaluate the contribution of each component:

Raw images
CLAHE preprocessing
Mask-only input
Full encryption + decryption
Biased decryption (proposed)
💡 Observation:

Performance gains are not due to preprocessing alone—
biased decryption introduces additional learning benefits beyond masking.

🔐 Security Metrics
NPCR: High (strong diffusion)
Entropy: Near ideal
Correlation: Low

👉 Ensures robustness of encryption while maintaining learnability.

📦 Tech Stack
Python
PyTorch
OpenCV
NumPy / SciPy
▶️ How to Run
git clone <repo-link>
cd project-folder
pip install -r requirements.txt
python train.py
🎥 Demo

(Add demo video / GIF here)

🌍 Applications
🧬 Medical Imaging (cell segmentation)
🧍 People Counting (privacy-preserving vision)
🤖 Robotics perception (edge AI)
🏙️ Smart surveillance systems
☁️ Distributed ML pipelines
⚠️ Limitations
Depends on quality of foreground mask
May remove useful background information
Additional compute overhead (encryption/decryption)
📌 Future Work
Extend to multi-domain datasets
Integrate with attention-based architectures
Optimize for real-time edge deployment
Explore theoretical grounding of inductive bias
🧠 Key Contribution

A hybrid cryptography–learning pipeline where data protection and representation learning are unified, enabling both privacy preservation and improved model performance.
