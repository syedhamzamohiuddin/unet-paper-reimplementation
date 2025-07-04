# 🧠 U-Net Paper Reimplementation — From Scratch and Faithful to the Original

Faithful implementation of the original U-Net architecture with weight maps, elastic deformation, and full training pipeline — based on the 2015 paper.

This project is a deep, from-scratch reimplementation of the original **U-Net: Convolutional Networks for Biomedical Image Segmentation** paper (Ronneberger et al., 2015).  
The implementation is divided into beginner-friendly **Kaggle notebooks**, each dedicated to a core component of the original architecture and training setup — **no shortcuts, no black boxes**.

> 📌 This repository serves as a landing page to the full notebook series and highlights what makes this implementation faithful to the original work.

---

## 🔗 Kaggle Notebook Series

| Part | Description | Link |
|------|-------------|------|
| Part 1 | U-Net Architecture from Scratch | [🔗 Notebook](https://www.kaggle.com/code/hamzamohiuddin/u-net-implementation-part-1-updated) |
| Part 2 | Elastic Deformation & Augmentation | [🔗 Notebook](https://www.kaggle.com/code/hamzamohiuddin/u-net-implementation-part-2) |
| Part 3 | Weight Map Generation | [🔗 Notebook](https://www.kaggle.com/code/hamzamohiuddin/u-net-implementation-part3/) |
| Part 4 | Dataset Preparation | [🔗 Notebook](https://www.kaggle.com/code/hamzamohiuddin/u-net-implementation-part-4/) |
| Part 5 | Training Loop & Results | [🔗 Notebook](https://www.kaggle.com/code/hamzamohiuddin/u-net-implementation-part-5) |
| Bonus | Elastic Deformation Explained in Depth | [🔗 Notebook](https://www.kaggle.com/code/hamzamohiuddin/elastic-deformation-detailed-explained) |

> 📌 Each notebook is structured, well-commented, and designed to be accessible for learners and reproducible for practitioners.

---

## 💡 What Makes This Different?

- ✅ Full U-Net architecture built **from scratch**, exactly as described in the original paper
- ✅ Implements **elastic deformation** using custom displacement fields and Gaussian smoothing
- ✅ Includes **pixel-wise weight map generation** to emphasize borders and handle class imbalance
- ✅ Reproducible **data preparation pipeline**: train/validation split, augmentation, and TFRecord generation
- ✅ Trains on **25,000+ augmented images using Kaggle TPUs** for massive speedup (TPU-VM v3-8)
- ✅ Covers **learning rate scheduling, callbacks, and checkpointing** in training
- ✅ Clean modular split: architecture · augmentation · weight maps · data prep · training
- ✅ Uses **public biomedical datasets** (e.g. ISBI-style microscopy)
- ✅ Beginner-friendly walkthroughs — with motivation, visualizations, and linked components


---


## ⚠️ Faithful to the Paper: What's Usually Done Wrong

Most public U-Net implementations deviate from the original 2015 paper in critical ways.  
This project avoids those shortcuts and replicates the original design as closely as possible:

- ❌ Uses `padding='same'` in conv layers  
  ✅ Uses **valid convolutions** with **manual input mirroring and padding** to preserve spatial structure
- ❌ Assumes auto-alignment of encoder–decoder paths  
  ✅ Performs **explicit cropping** to align encoder feature maps during concatenation
- ❌ Skips weight maps entirely  
  ✅ Includes **pixel-wise weight map generation** to emphasize border regions (as per the paper)
- ❌ Ignores elastic deformation  
  ✅ Implements **elastic deformation from scratch** using `scipy.ndimage`, matching the paper's core augmentation strategy for biomedical images

📌 This implementation is not just functional — it’s pedagogically faithful to the original U-Net design. If you're comparing U-Net repos, this one aims to teach *why* each detail matters.

---

## 🛠 Technologies Used

- Python · TensorFlow · Keras · NumPy · SciPy (`scipy.ndimage`) · Matplotlib
- Kaggle Notebooks for training and TPU execution
- Open-source biomedical datasets (e.g., ISBI, Cell Nuclei)

---

## 📘 Original Paper

> Ronneberger, Olaf, Philipp Fischer, and Thomas Brox.  
> ["U-Net: Convolutional Networks for Biomedical Image Segmentation."](https://arxiv.org/abs/1505.04597)  
> *arXiv preprint arXiv:1505.04597 (2015)*

---

## 🏷 Topics

U-Net · Semantic Segmentation · Biomedical Imaging · Deep Learning · Paper Reimplementation · Elastic Deformation · Keras · Image Segmentation

---

## 📥 Want the Code Here?

This repo currently links to well-structured Kaggle notebooks.  
A PyTorch/Keras codebase version may be added in the future. ⭐️ Watch the repo to get notified.

---

