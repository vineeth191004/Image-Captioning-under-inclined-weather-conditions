# Image Captioning Model

This repository provides an implementation of an Image Captioning model that uses MobileNetV2 for feature extraction and a combination of LSTM with attention mechanisms for generating descriptive captions for images.

## Table of Contents
1. [Introduction](#introduction)  
2. [Dataset Organization](#dataset-organization)  
3. [Model Details](#model-details)  
4. [Training and Evaluation](#training-and-evaluation)  
5. [Usage](#usage)   

---

## Introduction
Image captioning involves generating textual descriptions of images. This project uses a deep learning approach, combining a CNN (MobileNetV2) for extracting image features and an LSTM-based sequence generator with an attention mechanism.

---

## Dataset Organization
The dataset is divided into three subsets:
1. **Training - 1 Dataset**  
   - **Image Path**: `https://drive.google.com/drive/folders/1OkWH6p-KhzDLltDDeRz-KSoYSsL2kDCy?usp=sharing`  
   - **Annotations Path**: `https://github.com/vineeth191004/Image-Captioning-under-inclined-weather-conditions/blob/main/train_combined.json`  

2. **Training - 2 Dataset**  
   - **Image Path**: `https://drive.google.com/drive/folders/1-MSfhiaGbu8dHMiz5tcng9qHTdNBBZ0Z?usp=sharing`  
   - **Annotations Path**: `train2_combined.json`  

3. **Training - 3 Dataset**
   - **Image Path** : `https://drive.google.com/drive/folders/1saQvECFWUtyZkKFz5ZKQfFI2TMgyg7GG?usp=sharing`
   - **Annotations Path**: `sr_updated.json`

4. **Validation Dataset**
   - **Image Path** : `https://drive.google.com/drive/folders/1saQvECFWUtyZkKFz5ZKQfFI2TMgyg7GG?usp=sharing`
   - **Annotations Path**: `valid_combined.json`

5. **Testing Dataset**  
   - **Image Path**: `https://drive.google.com/drive/folders/1flIT8b3EqM6ifZvEAsXk92YSaF3wcwPY?usp=sharing`  
   - **Annotations Path**: `test_combined.json`  

**Note**: Update the paths above with your actual dataset locations before running the code.

---

## Model Details
1. **Feature Extraction**:  
   - MobileNetV2 processes images resized to 224x224 pixels and extracts high-level feature vectors.

2. **Sequence Generation**:  
   - Captions are tokenized and padded to a uniform length.
   - LSTM layers capture sequential dependencies.
   - Attention mechanism identifies the most relevant image features for each word.

3. **Beam Search**:  
   - Implements beam search during inference to enhance caption quality.

---

## Training and Evaluation
1. **Training**:  
   - The model trains for 30 epochs using training data.  
   - Dropout and dense layers are employed to generalize and optimize performance.  

2. **Evaluation Metrics**:  
   - **BLEU Score**: Measures n-gram precision relative to reference captions.  
   - **ROUGE Score**: Assesses overlap and sequence similarity between generated and reference captions.

---

Here is the updated README section with the cloning instructions:

---

## Usage

### Clone the Repository
To get started, clone this repository to your local machine using the following command:

```bash
git clone https://github.com/vineeth191004/Image-Captioning-under-inclined-weather-conditions.git
```

### Steps to Run
1. Navigate to the repository directory:
   ```bash
   cd Image-Captioning-under-inclined-weather-conditions
   ```
2. Set up the dataset by organizing images and annotations into directories as specified in the paths in the dataset section.
3. Train the model using:
   ```bash
   python train_model.py --dataset /path/to/dataset
   ```
4. Evaluate the model using:
   ```bash
   python evaluate_model.py --model saved_model.pth --dataset /path/to/validation
   ```

---

Let me know if further refinements are needed!
