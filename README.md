# Wonders of the World – Image Classification 🌍

A Deep Learning project that classifies images of **12 famous world landmarks** using Convolutional Neural Networks (CNNs) and Transfer Learning with **ResNet50V2**.

The project explores automated landmark recognition using image preprocessing, data augmentation, transfer learning, and multi-class image classification.

## 📌 Project Overview

Recognizing landmarks from images is a challenging computer vision task due to variations in camera angles, lighting conditions, backgrounds, and architectural similarities.

This project implements a 12-class image classification model using a pretrained ResNet50V2 backbone to extract meaningful visual features and classify landmark images.

### Objectives

- Build an image classification model for 12 world-famous landmarks.
- Apply Transfer Learning using ResNet50V2.
- Improve model generalization through data augmentation.
- Evaluate model performance using multiple classification metrics.
- Analyze predictions and misclassifications using a confusion matrix.

## 🏛️ Landmark Categories

The model classifies images into the following 12 categories:

1. Burj Khalifa
2. Chichen Itza
3. Christ the Redeemer
4. Eiffel Tower
5. Great Wall of China
6. Machu Picchu
7. Pyramids of Giza
8. Roman Colosseum
9. Statue of Liberty
10. Stonehenge
11. Taj Mahal
12. Angel Falls

## 🧠 Model Architecture

The project uses **ResNet50V2**, a deep residual neural network pretrained on ImageNet, as a feature extractor.

The architecture consists of:

1. **Input Layer:** Accepts RGB images of size `400 × 400 × 3`.
2. **Data Augmentation:** Applies random transformations to improve generalization.
3. **ResNet50V2:** Extracts deep visual features using a frozen pretrained backbone.
4. **Global Average Pooling:** Reduces spatial feature dimensions.
5. **Dense Layer:** Performs classification across 12 landmark categories using Softmax activation.

### Architecture Flow

```text
Input Image (400 × 400 × 3)
          |
          v
   Data Augmentation
          |
          v
   ResNet50V2 Backbone
    (Pretrained & Frozen)
          |
          v
 Global Average Pooling
          |
          v
    Dense Layer
     (12 Classes)
          |
          v
  Softmax Prediction
```

## ⚙️ Data Preprocessing & Augmentation

The dataset is divided into training and validation sets using an **80:20 split**.

The following augmentation techniques are applied during training:

- Random Horizontal Flip
- Random Rotation (±20%)
- Random Zoom (±20%)
- Random Height Shift
- Random Width Shift
- Pixel Rescaling (0–1 normalization)

These transformations help the model generalize better to variations in real-world landmark images.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Programming Language |
| TensorFlow | Deep Learning Framework |
| Keras | Model Development |
| ResNet50V2 | Transfer Learning |
| NumPy | Numerical Computation |
| Matplotlib | Visualization |
| Scikit-learn | Model Evaluation |
| Jupyter Notebook | Development Environment |

## 📊 Model Training

The model is trained using the following configuration:

| Parameter | Value |
|---|---|
| Architecture | ResNet50V2 |
| Input Image Size | 400 × 400 × 3 |
| Number of Classes | 12 |
| Batch Size | 32 |
| Optimizer | Adam |
| Learning Rate | 0.001 (default) |
| Loss Function | Categorical Cross-Entropy |
| Epochs | 5 |
| Label Encoding | One-Hot Encoding |
| Backbone | Frozen |

The training process also uses:

- ModelCheckpoint to save the best model based on validation accuracy.
- CSVLogger to record training history.
- TensorBoard for training visualization.

## 📈 Evaluation Metrics

The model's performance is evaluated using:

- **Accuracy:** Measures overall classification correctness.
- **Precision:** Measures the correctness of positive predictions.
- **Recall:** Measures how many actual class instances are correctly identified.
- **F1-Score:** Provides a balance between precision and recall.
- **Confusion Matrix:** Helps identify correctly classified and misclassified landmark images.

## 📁 Repository Structure

```text
Wonders-of-the-World-Image-Classification/
│
├── CV - Image classification Notebook.ipynb
│
├── WondersClassification_Presentation.pptx
│
├── DLL Report.pdf
│
├── README.md
│
└── requirements.txt
```

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Udaykaran-Singh/Wonders-of-the-World-Image-Classification.git
```

### 2. Navigate to the Project Directory

```bash
cd Wonders-of-the-World-Image-Classification
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it:

**macOS / Linux**
```bash
source venv/bin/activate
```

**Windows**
```bash
venv\Scripts\activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the Notebook

```bash
jupyter notebook
```

Open `CV - Image classification Notebook.ipynb` and execute the cells.

**Note:** The dataset is not included in this repository. You will need to configure the dataset path in the notebook before running the training pipeline.

## 🔮 Future Improvements

- Fine-tune deeper ResNet50V2 layers.
- Experiment with EfficientNet and other pretrained architectures.
- Increase dataset size and diversity.
- Improve performance on visually similar landmarks.
- Explore ensemble learning techniques.
- Deploy the trained model through a web-based interface.

## 📚 References

1. He, K. et al. (2016). *Identity Mappings in Deep Residual Networks*. ECCV 2016.
2. [TensorFlow Documentation](https://www.tensorflow.org/)
3. Chollet, F. (2021). *Deep Learning with Python*. Manning Publications.

---

**Developed as part of the Deep Learning Laboratory (DLL) project.**
