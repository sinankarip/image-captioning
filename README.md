
# Image Captioning Project
An end-to-end image captioning project using Blip

## 📋 Project Overview

A pipeline for generating descriptive captions from images. The goal is to deliver accurate, human-like captions using deep learning architectures, while navigating resource constraints and optimizing performance.

---

## 🚩 Problem Statement

* **Resource bottleneck:** Limited GPU memory and compute caused extremely long processing times and frequent kernel crashes.
* **Overfitting challenges:** Initial CNN–LSTM and Transformer models struggled to generalize.
* **Caption length gap:** Pre-trained BLIP generated captions of only 7–8 words, whereas the test set captions average 17–18 words.

---

## 🗄️ Dataset Handling

* **Original dataset:** Full image set.
* **Subsetting strategy:** Divided the dataset into smaller subsets and processed in batches to reduce memory footprint and prevent crashes.
* **Batching:** Implemented batched data loading and processing to optimize runtime and keep kernel stable.

---

## 🛠️ Model Architectures & Experiments

1. **CNN–LSTM**

   * Built end-to-end pipeline for visual feature extraction (CNN) and sequence generation (LSTM).
   * **Outcome:** High overfitting; training loss decreased but validation performance stalled.

2. **Transformer**

   * Replaced recurrent layers with self-attention blocks.
   * **Outcome:** Training stability improved, but final captions did not meet quality or length expectations.

3. **BLIP (Bootstrapping Language–Image Pre-training)**

   * Applied pre-trained BLIP out of the box.
   * **Without fine-tuning:** Produced short captions (7–8 words).
   * **With fine-tuning:** Achieved convincing and contextually rich captions matching average test-set length (\~17–18 words).

---


## 🔮 Future Improvements

* **Data augmentation:** Apply image blurring or other augmentations to enrich training signals.
* **Expand subset size:** Increasing the subset for fine-tuning may enhance caption detail and diversity.
* **Hybrid models:** Explore combining CNN–LSTM with attention mechanisms to balance overfitting and performance.
* **Hyperparameter tuning:** Systematic grid search on learning rate, batch size, and architecture depth.

---

*Readme generated to document key decisions and streamline future development.*
