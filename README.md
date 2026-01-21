# Computer-Vision---2024-2025---Leonardo-Bisazza---1762939

# Project 8: Invisibility Cloak for Depth Deception

### Adversarial Attacks on Monocular Depth Estimation

**Course:** Computer Vision (Prof. Irene Amerini) - Sapienza University of Rome

**Student:** Leonardo Bisazza 1762939

---

## 📖 Project Description

This project investigates the vulnerability of Monocular Depth Estimation models to adversarial attacks.
Based on the "Project 8" specifications, we adapted the **"Invisibility Cloak"** concept—originally designed for 2D object detection—to target the **Depth Anything V2** architecture.

The primary objective is to generate **physical adversarial patches** that, when applied to target objects (e.g., refrigerators, TVs), manipulate depth predictions. These patches create "depth punctures" (increasing perceived distance) or full concealment effects, effectively making objects "invisible" to the geometric reconstruction of the model.

## 🚀 Key Features

* **Baseline Training:** Fine-tuning and adaptation of the model on the **NYU Depth V2** dataset.
* **Digital Attack:** Generation of adversarial patches robust to transformations using **Expectation-Over-Transformation (EOT)**.
* **Physical Validation:** A complete pipeline to test printed patches in real-world scenes (kitchen, living room) under varying lighting conditions.
* **Portable Code:** A self-contained notebook optimized for Google Colab, featuring automated data and weight management without rigid dependencies on Google Drive.

---

## 🛠️ Execution Instructions

The notebook is designed to be **self-consistent**. Required files will be requested interactively during execution.

### Prerequisites

Ensure you have the following files on your local machine:

1. `kaggle.json`: API Token required to download the NYUv2 dataset.
2. `latest.pth`: Trained model checkpoint (optional, if you wish to use our weights).

### Steps

1. Open the notebook `vision_project_Depth_Anything_V2.ipynb` in **Google Colab**.
2. Execute all cells in sequence.
3. **Kaggle Token Upload:** When prompted, upload your `kaggle.json` file.
4. **Checkpoint Loading:**
* If you have the `latest.pth` file, select the manual upload option when prompted.
* Otherwise, the system will automatically download the pre-trained base model to allow for inference.



---

## 📂 Notebook Structure

1. **Environment Configuration:** Variable setup and repository cloning.
2. **Dataset Download:** Retrieval of the NYU Depth V2 data.
3. **Training Loop:** Core training code (checkpoints saved to `./checkpoints`).
4. **Adversarial Patch Generation:** Optimization of the digital adversarial pattern.
5. **Digital Validation:** Quantitative evaluation on the test dataset.
6. **Physical Validation:**
* Uploading real-world photos (with/without patches).
* Inference and side-by-side visualization of the predicted depth maps.



---

## 🔗 Credits & References

* **Project Reference:** Project 8 - Computer Vision Course, Sapienza University.
* **Base Model:** [Depth Anything V2](https://github.com/DepthAnything/Depth-Anything-V2)
* **Dataset:** [NYU Depth V2](https://cs.nyu.edu/~silberman/datasets/nyu_depth_v2.html)
* **Key Paper:** Thys, S., Van Ranst, W., & Goedemé, T. (2019). "Fooling automated surveillance cameras: adversarial patches to attack person detection".

