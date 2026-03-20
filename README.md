<div align="center">

# 🌿 LW3 — Custom Image Classifier

**A plant species image classifier built with TensorFlow and trained on Google Colab.**

[![Open in Colab](https://img.shields.io/badge/Open%20in-Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)](https://colab.research.google.com/drive/1qy31Hun2fxkCpeV0CWc2qBBjvuTY94_W?usp=sharing)

</div>

---

## 📋 Project Overview

This project is a custom image classifier that can identify **20 different plant species** from images. I trained a CNN model using TensorFlow on Google Colab with a dataset of over **5,000 images**. The project covers dataset preparation, model training, performance analysis, and model improvement techniques like data augmentation, dropout, and early stopping.

---

## 🔗 Google Colab Link

You can view the full notebook here:

> **[Open in Google Colab →](https://colab.research.google.com/drive/1qy31Hun2fxkCpeV0CWc2qBBjvuTY94_W?usp=sharing)**

---

## 📂 1. Dataset Preparation

**How did you organize your dataset in Google Drive?**

I put all my dataset into one folder in Google Drive called `ImageSet`. Inside that, I made separate folders for each plant type — for example, `Barberries`, `Fuchsia`, `Forsythia`, and more. Each folder had pictures of that specific plant. TensorFlow used the folder names to know which pictures belonged to which plant type.

**Why is folder structure important for TensorFlow image loading?**

The folder structure matters a lot. TensorFlow looks at the folder names to figure out what kind of pictures are in them. If the pictures aren't in the right folders, TensorFlow will get confused and assign wrong labels. A good folder structure makes it easy and fast to get your dataset ready.

---

## 🧠 2. Model Training

**What is the role of layers in image classification?**

Convolutional layers help find things in pictures — they look for edges, shapes, and textures. This helps the model tell plant types apart based on how they look.

**Why do we split data into training and validation sets?**

We split the data so the model can learn from some pictures and then test on others it hasn't seen before. This helps us see if the model is actually learning or just memorizing the training images.

---

## 📊 3. Performance Analysis

**What accuracy did your model achieve?**

My model got **52.57% accuracy** on the validation set. When I tested it on a picture of Barberries, it correctly said it was Barberries with **99.28% confidence**.

**How did the number of images affect the model's performance?**

Having a lot of images helped my model learn. I used over 5,000 images of 20 plant types. This gave the model many different pictures to learn from, but it also made things harder because there were so many types to tell apart.

---

## 🤔 4. Critical Thinking

**What challenges did you encounter while using your dataset?**

- It took a long time to load and train the model, especially with Google Drive.
- I had to make sure all the folders and file names were correct. If they weren't, TensorFlow wouldn't work properly.
- Some plant pictures looked really similar to each other, which made it hard for the model to tell them apart.

**How can data augmentation improve your model?**

Data augmentation helps by creating new pictures from the ones you already have — like flipping or rotating them. This gives the model more variety to learn from, and helps it not get too focused on one specific version of an image. It makes the model better at recognizing plants in general.

---

## 💡 5. Application

**Suggest a real-world application for your trained model.**

This model could be used as a plant identification tool. Someone can upload a picture of a plant and the system will tell them what type it is. This could help students, gardeners, and researchers who want a quick way to identify plants.

**How can this system be integrated into a web application?**

The system can be put into an app or website. Users can upload a picture or take one with their camera, and the app will send it to the model and show what type of plant it is. This can be done with **TensorFlow Lite** for mobile apps, or with a **Python backend** (like Flask or FastAPI) for web apps.

---

## 🔧 6. Model Improvement

---

**What signs indicated overfitting in my model?**

My first model showed overfitting. The training accuracy got very high, but the validation accuracy stayed low. The training loss kept going down while the validation loss started going up. This means the model learned the training images too well and didn't do well with new images it hadn't seen before.

**How did data augmentation affect validation accuracy?**

Data augmentation helped. It showed the model different versions of the training images — like flipped and rotated ones. My improved model did better on validation images and had less overfitting. It helped the model learn in a more balanced way.

**What is the purpose of dropout layers?**

Dropout layers help reduce overfitting. They randomly turn off some neurons during training, which stops the model from relying too much on specific features. This way, it learns in a more balanced way and does better on new data.

**Why does data augmentation improve generalization?**

Data augmentation adds variety to the training data. The model sees different versions of the same images, so it becomes less sensitive to exact positions and sizes of objects in the pictures. This helps it classify new images more effectively.

---

## 📈 7. Performance Comparison

**Compare accuracy before and after improvements.**

| Model | Validation Accuracy |
|---|---|
| First Model (Baseline) | 52.57% |
| Improved Model (Best) | 53.36% |

> The accuracy difference wasn't huge, but the training and validation curves got closer together in the improved model. This means the improved model had better generalization and less overfitting.

**Which technique contributed most to improvement?**

I think **data augmentation** and **dropout** helped the most. They directly reduced overfitting — data augmentation added variety to the training images, and dropout prevented the model from memorizing the data too much. **Early stopping** also helped by stopping the training when the validation performance stopped improving.

---

## 🚀 8. Deployment

**Why is saving the model important?**

Saving the model is important because it lets me reuse the trained model later without having to retrain it. This saves time and resources, and makes the model ready for deployment in applications like websites or mobile apps.

**How can this model be deployed in a real-world system?**

This model can be deployed in a real-world system by integrating it into a web or mobile application:

- **Mobile App** — Using TensorFlow Lite, a user can capture an image of a plant, and the app predicts the plant type right on the device.
- **Web App** — The model can be connected through a backend framework like Flask or FastAPI. Users upload an image through the website, and the model returns the prediction.

---

<div align="center">

**Built with TensorFlow · Trained on Google Colab**

</div>
