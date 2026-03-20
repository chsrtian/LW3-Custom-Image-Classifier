<div align="center">

# 🌿 Custom Image Classifier — Plant Species Recognition

**A deep learning image classification model trained to identify 20 plant species using TensorFlow and Google Colab.**

[![Open in Colab](https://img.shields.io/badge/Open%20in-Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)](https://colab.research.google.com/drive/1qy31Hun2fxkCpeV0CWc2qBBjvuTY94_W?usp=sharing)

</div>

---

## 📋 Project Overview

This project builds a **Convolutional Neural Network (CNN)** to classify images of plants into one of **20 species categories**. The model is trained on a dataset of over **5,000 images** organized by species, leveraging TensorFlow's image loading utilities and data augmentation techniques. The project explores model improvement strategies including **dropout regularization**, **data augmentation**, and **early stopping** to combat overfitting and improve generalization.

---

## 🔗 Google Colab Link

Access the full notebook with code, outputs, and training history:

> **[Open Notebook in Google Colab →](https://colab.research.google.com/drive/1qy31Hun2fxkCpeV0CWc2qBBjvuTY94_W?usp=sharing)**

---

## 📂 Dataset Preparation

### How was the dataset organized in Google Drive?

The dataset was stored in a root folder called `ImageSet` on Google Drive. Inside this folder, each plant species had its own dedicated subfolder (e.g., `Barberries`, `Fuchsia`, `Forsythia`, etc.), with each subfolder containing images of that specific plant type. TensorFlow uses these folder names as class labels, automatically mapping each image to its corresponding category.

### Why is folder structure important for TensorFlow image loading?

> **Key Insight:** TensorFlow relies on the directory hierarchy to infer class labels. If images are misplaced or folder names are inconsistent, the model will assign incorrect labels — leading to poor or unpredictable results.

A well-organized folder structure ensures:
- **Automatic label assignment** — folder names become class names.
- **Efficient data loading** — TensorFlow can batch and shuffle data seamlessly.
- **Reproducibility** — a clean structure makes the pipeline easy to understand and reuse.

---

## 🧠 Model Training

### What is the role of convolutional layers in image classification?

Convolutional layers are the backbone of image classification models. They extract spatial features from images by scanning for:

- **Edges** and outlines
- **Shapes** and structural patterns
- **Textures** and fine-grained details

These learned features allow the model to distinguish between different plant species based on their visual characteristics.

### Why do we split data into training and validation sets?

Splitting the data serves a critical purpose:

| Set | Purpose |
|---|---|
| **Training Set** | Used to teach the model by adjusting its weights based on labeled examples. |
| **Validation Set** | Used to evaluate the model on unseen data and detect overfitting. |

Without a validation set, there is no way to determine whether the model is genuinely learning generalizable patterns or simply memorizing the training images.

---

## 📊 Performance Analysis

### What accuracy did the model achieve?

| Metric | Value |
|---|---|
| Validation Accuracy | **52.57%** |
| Test Prediction (Barberries) | **99.28% confidence** (correctly classified) |

The model achieved a validation accuracy of **52.57%**. When tested on a sample image of *Barberries*, it correctly predicted the species with **99.28% confidence**.

### How did the number of images affect performance?

The dataset contained over **5,000 images** spanning **20 plant species**. While the large number of images provided diverse training examples, the high number of classes (20) made the classification task more challenging. With more classes, the model must learn finer distinctions between visually similar species.

---

## 🤔 Critical Thinking

### What challenges were encountered while using the dataset?

Several challenges arose during training:

- **Long load and training times** — particularly when mounting and reading data from Google Drive.
- **File and folder naming issues** — incorrect names or misplaced files caused TensorFlow to fail during data loading.
- **Visual similarity between species** — some plant types share similar features (e.g., leaf shape, color), making it difficult for the model to differentiate between them.

### How can data augmentation improve the model?

Data augmentation generates new training samples by applying transformations (e.g., rotation, flipping, zooming) to existing images. This:

- **Increases the effective dataset size** without collecting new data.
- **Reduces overfitting** by exposing the model to varied representations.
- **Improves generalization** — the model becomes more robust to changes in orientation, scale, and position.

---

## 💡 Application

### Real-world application for the trained model

This model can serve as the core of a **plant identification tool**. Users could upload or capture a photo of a plant, and the system would predict its species. Potential use cases include:

- 🌱 **Students** — learning to identify plant species for coursework.
- 🌻 **Gardeners** — identifying unknown plants in their garden.
- 🔬 **Researchers** — rapid preliminary classification in field studies.

### How can this system be integrated into a web application?

The model can be deployed through multiple channels:

- **Mobile App** — using **TensorFlow Lite** for on-device inference, enabling users to take a photo and get instant results.
- **Web Application** — serving the model through a Python backend (e.g., **Flask** or **FastAPI**), where users upload images via a web interface and receive predictions in real time.

---

## 🔧 Model Improvement

### Part 2 — Addressing Overfitting

---

### 1. What signs indicated overfitting in the initial model?

The first model showed clear signs of overfitting:

| Indicator | Training | Validation |
|---|---|---|
| **Accuracy** | Very high ↑ | Remained low ↓ |
| **Loss** | Kept decreasing ↓ | Started increasing ↑ |

> **Interpretation:** The model memorized the training data but failed to generalize to unseen validation images — a textbook case of overfitting.

### 2. How did data augmentation affect validation accuracy?

After applying data augmentation (flipping, rotation, etc.), the improved model showed:

- **Better performance** on validation images.
- **Reduced gap** between training and validation metrics.
- **More balanced learning** — the model became less reliant on memorized training examples.

### 3. What is the purpose of dropout layers?

Dropout layers randomly deactivate a fraction of neurons during each training step. This prevents the model from becoming overly dependent on specific features and encourages it to learn more distributed, robust representations — leading to better generalization on new data.

### 4. Why does data augmentation improve generalization?

Data augmentation introduces variability into the training set by presenting transformed versions of the same images. The model becomes:

- Less sensitive to **object position** and **orientation**.
- More capable of handling **scale variations**.
- Better at classifying images it has never seen before.

---

## 📈 Performance Comparison

### Accuracy before and after improvements

| Model Version | Validation Accuracy |
|---|---|
| **Baseline Model** | 52.57% |
| **Improved Model** | 53.36% (best) |

> **Note:** While the numerical improvement was modest, the training and validation curves converged more closely in the improved model, indicating **better generalization** and **reduced overfitting**.

### Which technique contributed most to improvement?

The most impactful techniques were:

1. **Data Augmentation** — added variety to the training images, reducing the risk of overfitting.
2. **Dropout Layers** — prevented the model from memorizing training data by randomly disabling neurons.
3. **Early Stopping** — halted training when validation performance stopped improving, avoiding unnecessary overfitting.

---

## 🚀 Deployment

### Why is saving the model important?

Saving the trained model is essential because:

- **Eliminates retraining** — the model can be loaded and used instantly without repeating the training process.
- **Saves time and compute resources** — training is the most expensive step.
- **Enables deployment** — a saved model can be integrated directly into web or mobile applications.

### How can this model be deployed in a real-world system?

| Deployment Target | Technology | Workflow |
|---|---|---|
| **Mobile Application** | TensorFlow Lite | User captures an image → on-device model predicts the plant species → result displayed instantly. |
| **Web Application** | Flask / FastAPI | User uploads an image via the web interface → backend sends it to the model → prediction is returned and displayed. |

---

<div align="center">

**Built with TensorFlow · Trained on Google Colab**

</div>
