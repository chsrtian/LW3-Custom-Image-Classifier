<div align="center">

# 🌿 LW3 — Custom Image Classifier

A plant image classifier I built using TensorFlow and Google Colab.  
It can classify **20 different plant species** from images.

[![Open in Colab](https://img.shields.io/badge/Open%20in-Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)](https://colab.research.google.com/drive/1qy31Hun2fxkCpeV0CWc2qBBjvuTY94_W?usp=sharing)

</div>

---

##  Google Colab Link

You can view the full notebook here:  
[https://colab.research.google.com/drive/1qy31Hun2fxkCpeV0CWc2qBBjvuTY94_W?usp=sharing](https://colab.research.google.com/drive/1qy31Hun2fxkCpeV0CWc2qBBjvuTY94_W?usp=sharing)

---

## 📂 1. Dataset Preparation

### How did you organize your dataset in Google Drive?

I put all my dataset into one folder in Google Drive called `ImageSet`. Then I made folders inside `ImageSet` for each type of plant. For example, I had folders for Barberries, Fuchsia, Forsythia, and more. Each folder had pictures of that plant type. TensorFlow used the folder names to know which pictures belonged to which plant type.

### Why is folder structure important for TensorFlow image loading?

The way you organize your folders is important because TensorFlow looks at the folder names to know what kind of pictures are in them. If the pictures are not in the right folders, TensorFlow will get confused. A good folder structure makes it easy and fast to get your dataset ready.

---

## 🧠 2. Model Training

### What is the role of layers in image classification?

Convolutional layers help find things in pictures. They look for edges, shapes, and textures. This helps the model tell plant types apart.

### Why do we split data into training and validation sets?

We split the data so the model can learn from some pictures and then test on others it hasn't seen before. This helps us see if the model is really learning or just memorizing.

---

## 📊 3. Performance Analysis

### What accuracy did your model achieve?

My model got **52.57% accuracy** on the validation set. When I tested it on a picture of Barberries, it correctly said it was Barberries with **99.28% confidence**.

### How did the number of images affect the model's performance?

Having more images helped my model learn. I used over **5,000 images** of **20 plant types**. This helped the model see different pictures, but it also made it harder because there were many types to tell apart.

---

## 🤔 4. Critical Thinking

### What challenges did you encounter while using your dataset?

- It took a long time to load and train the model, especially with Google Drive.
- I had to make sure the folders and file names were right. If they weren't, TensorFlow wouldn't work.
- Some plant pictures looked similar, which made it hard for the model to tell them apart.

### How can data augmentation improve your model?

Data augmentation helps by creating new versions of pictures from old ones — like flipping or rotating them. This makes the model better at recognizing plants because it sees different versions of each picture. It helps the model not get too focused on just one look and to work better overall.

---

## 💡 5. Application

### Suggest a real-world application for your trained model.

This model can be used to identify plant types. Someone can upload a picture of a plant and the system will say what type it is. This can help students, gardeners, and researchers.

### How can this system be integrated into a web application?

This system can be put into an app or website. Users can upload a picture or take one with their camera. The app will send the picture to the model and show what type of plant it is. This can be done with TensorFlow Lite on mobile, or with a Python backend on the web.

---

---

# Part 2 — Model Improvement & Analysis

---

## 🔍 6. Overfitting & Data Augmentation

### What signs indicated overfitting in my model?

My first model showed overfitting. The training accuracy got very high, but the validation accuracy stayed low. The training loss kept going down, while the validation loss started going up. This means the model learned the training images too well and did not do well with new validation images.

### How did data augmentation affect validation accuracy?

Data augmentation helped. It showed the model different versions of the training images, like flipped and rotated ones. My improved model did better on validation images and had less overfitting. It helped the model learn in a more balanced way.

---

## 🔧 7. Model Improvement

### What is the purpose of dropout layers?

Dropout layers help reduce overfitting. They randomly turn off some neurons during training. This helps the model not rely too much on specific features. It learns in a more balanced way and does better on new data.

### Why does data augmentation improve generalization?

Data augmentation helps because it adds variety to the training data. The model sees different versions of the same images, so it becomes less sensitive to the exact positions and sizes of objects. It can classify images more effectively because of this.

---

## 📈 8. Performance Comparison

### Compare accuracy before and after improvements.

| Model | Validation Accuracy |
|---|---|
| First Model (Baseline) | 52.57% |
| Improved Model (Best) | 53.36% |

It was not a big change in numbers, but the training and validation curves got closer together. The improved model had better generalization and less overfitting.

### Which technique contributed most to improvement?

I think data augmentation and dropout helped the most. They directly reduced overfitting. Data augmentation added variety to the training images, and dropout prevented the model from memorizing the data too much. Early stopping also helped by stopping the training when validation performance stopped improving.

---

## 🚀 9. Deployment

### Why is saving the model important?

Saving the model is important because it lets me reuse the trained model later. I don't have to retrain it every time. It saves time and resources, and it makes the model ready for deployment in applications like websites and mobile apps.

### How can this model be deployed in a real-world system?

This model can be deployed in a real-world system by integrating it into a web or mobile application. Users can capture an image of a plant, and the application sends the image to the trained model. The model predicts the plant class and returns the result.

- **On mobile** — this can be done using **TensorFlow Lite**.
- **On the web** — the model can be connected through a backend framework like **Flask** or **FastAPI**.

---

<div align="center">

**Built with TensorFlow · Trained on Google Colab**

</div>
