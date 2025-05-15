# NeuroFusion: A Unified Framework for Generalized Visual Stimulus Decoding from fMRI Across Datasets and Subjects

This repository contains code for the paper:

**"NeuroFusion: A Unified Framework for Generalized Visual Stimulus Decoding from fMRI Across Datasets and Subjects"**

---

## 🧠 Abstract

Recent advancements in neural decoding have shown promising results in reconstructing visual experiences from brain activity. However, existing approaches primarily focus on decoding within a single dataset or subject, which limits generalization across diverse neuroimaging sources. In this work, we propose a novel framework for cross-subject and cross-dataset brain decoding of visual stimuli, integrating neural recordings from multiple publicly available fMRI datasets. To address inherent inter-subject and inter-dataset variability, we introduce a contrastive learning-based alignment strategy using image embeddings from a pretrained IP-Adapter model. Our approach learns a shared latent space by aligning subject-specific neural representations with image features, enabling generalized decoding across both subjects and datasets. In addition, we propose a simple yet effective data augmentation method using ridge regression. This method synthesizes realistic fMRI-like signals from novel images by predicting voxel activity and injecting learned noise distributions, thereby enhancing training diversity and model robustness. To the best of our knowledge, while several recent studies have explored cross-subject decoding, our work is the first to extend this direction to joint decoding across multiple datasets and subjects using a unified training framework. Empirical results show that our method achieves competitive and, in some metrics, state-of-the-art decoding performance under this more challenging and realistic setting. These findings highlight the potential of dataset-agnostic neural decoding and provide new directions for developing generalizable brain-computer interfaces.

---

## 📁 Repository Structure

| File | Description |
|------|-------------|
| `matrices.ipynb` | Computes quantitative evaluation metrics (PixCorr, SSIM, Top-1 Accuracy, etc.). |
| `BOLD5000_data_augmentation.ipynb` | Data augmentation pipeline for the BOLD5000 dataset. |
| `GOD_SemanticDecoding.ipynb` | Loads and processes the GOD dataset for semantic decoding. |
| `GOD_data_augmentation.ipynb` | Data augmentation for the GOD dataset. |
| `GOD_dataloader.ipynb` | Preprocessing and dataloader setup for GOD dataset. |
| `GOD_decoding_utils.py` | Helper functions for processing GOD dataset. |
| `NSD_data_augmentation.ipynb` | Data augmentation strategy for the NSD dataset. |
| `cross_model_aligment.ipynb` | Core notebook implementing the cross-model alignment method used for decoding. |
| `NSD_dataloader_utils.ipynb` | Dataloader and embeddings extractions for NSD dataset |

---

## 📦 Datasets

To replicate the experiments, download and prepare the following datasets:

- **NSD (Natural Scenes Dataset)**  
  Download from: [https://naturalscenesdataset.org/](https://naturalscenesdataset.org/)  
  - Includes high-resolution fMRI responses from 8 subjects viewing thousands of natural images. We used subject 1,2,5,7 in this study

- **BOLD5000**  
  Download from: [https://bold5000-dataset.github.io/website/](https://bold5000-dataset.github.io/website/)  
  - Contains fMRI responses of 4 subjects to 5,000 visual stimuli from COCO, ImageNet, and Scene datasets.

- **GOD (Generic Object Decoding)**  
  Download from: [https://openneuro.org/datasets/ds001246/versions/1.2.1](https://openneuro.org/datasets/ds001246/versions/1.2.1)  
  - Includes visual object categories and corresponding fMRI responses.

---

## 🖼️ ImageNet Data (for Augmentation)

We used a subset of the **ImageNet (ILSVRC2012)** dataset for generating image augmentations.  
To access it, download from the kaggle repository:

- [https://www.kaggle.com/datasets/thbdh5765/ilsvrc2012](https://www.kaggle.com/datasets/thbdh5765/ilsvrc2012)  


