# SpiderVerse_Classification

🚀 **Live Demo:**
👉 **https://spiderverseclassification.streamlit.app/**

Upload any Spider-Verse character image and the model predicts the character instantly.

---

## Overview

This project builds a **deep learning based Spider-Verse character classifier** using multiple modern computer vision architectures and compares their performance.

The system can identify the following characters:

* Miles Morales
* Peter B. Parker
* Gwen Stacy
* Pavitr Prabhakar
* Miguel O'Hara
* Hobie Brown (Spider-Punk)
* Spider-Ham
* Spider-Man Noir

The project explores **CNN transfer learning and YOLO classification** and deploys the best model as a **live web application**.

---

## Project Highlights

* Transfer learning with **ResNet50**
* Lightweight CNN with **MobileNetV2**
* Ultra-fast classification using **YOLOv8-Nano**
* Data augmentation pipeline for small datasets
* Real-time webcam classification
* Streamlit web application deployment
* Live public demo

---

## Live Application

You can try the model directly here:

👉 **https://spiderverseclassification.streamlit.app/**

Steps:

1. Upload an image
2. The model analyzes the image
3. The predicted Spider-Verse character is displayed

---

## Repository Structure

```
SpiderVerse_Classification
│
├── dataset/
│
├── dataset_split/
│   ├── train/
│   ├── val/
│   └── test/
│
├── notebooks/
│   ├── data_augmentation.ipynb
│   ├── resnet_training.ipynb
│   ├── yolov8_training.ipynb
│
├── deployment/
│   ├── webcam_classifier.py
│   ├── streamlit_app.py
│
├── models/
│   └── best.pt
│
├── requirements.txt
│
└── README.md
```

---

## Dataset

The dataset contains Spider-Verse characters from **Spider-Man: Into the Spider-Verse** and **Across the Spider-Verse**.

### Classes

| Class | Character        |
| ----- | ---------------- |
| 0     | Miles Morales    |
| 1     | Peter B. Parker  |
| 2     | Gwen Stacy       |
| 3     | Pavitr Prabhakar |
| 4     | Miguel O'Hara    |
| 5     | Hobie Brown      |
| 6     | Spider-Ham       |
| 7     | Spider-Man Noir  |

### Dataset Size

| Split      | Images |
| ---------- | ------ |
| Train      | ~2024  |
| Validation | ~503   |
| Test       | ~635   |

Images were augmented using:

* rotation
* zoom
* brightness shift
* horizontal flip
* shear transformation

This helped increase dataset diversity.

---

## Model Architectures

### 1. ResNet50 (Transfer Learning)

The project uses **ResNet50 pretrained on ImageNet**.

Architecture highlights:

* 50 layers deep
* residual skip connections
* bottleneck blocks
* global average pooling

Training strategy:

1. Freeze pretrained backbone
2. Train custom classification head
3. Fine-tune final layers

Final performance:

**Test Accuracy:** ~98.9%

---

### 2. MobileNetV2

MobileNetV2 was also tested as a lightweight architecture.

Advantages:

* fewer parameters
* faster inference
* suitable for mobile devices

Performance:

**Validation Accuracy:** ~97%

---

### 3. YOLOv8 Nano Classification

The project also evaluates **YOLOv8-Nano classification model**.

Model characteristics:

* ~1.4M parameters
* extremely fast inference
* suitable for real-time applications

Results:

| Metric         | Value  |
| -------------- | ------ |
| Top-1 Accuracy | ~99.8% |
| Top-5 Accuracy | 100%   |

Inference speed:

**~2 ms per image**

---

## Model Comparison

| Model       | Parameters | Accuracy |
| ----------- | ---------- | -------- |
| MobileNetV2 | ~3.5M      | ~97%     |
| ResNet50    | ~25M       | ~98.9%   |
| YOLOv8-Nano | ~1.4M      | ~99.8%   |

YOLOv8 achieved the **best balance of speed and accuracy**.

---

## Real-Time Webcam Classification

The trained model can run on a webcam for live predictions.

Example workflow:

```
Camera Frame
      ↓
YOLOv8 Classifier
      ↓
Predicted Character
      ↓
Displayed on screen
```

This allows real-time Spider-Verse character recognition.

---

## Streamlit Deployment

The project is deployed using **Streamlit** to create an interactive web interface.

Users can:

* upload an image
* run the model inference
* see the predicted Spider-Verse character

The application is publicly accessible.

👉 **https://spiderverseclassification.streamlit.app/**

---

## Installation

Clone the repository:

```
git clone https://github.com/BhuvanMohan2005/SpiderVerse_Classification.git
cd SpiderVerse_Classification
```

Install dependencies:

```
pip install -r requirements.txt
```

---

## Running the Streamlit App Locally

```
streamlit run app.py
```

Then open:

```
http://localhost:8501
```

---

## Running Webcam Detection

```
python webcam_classifier.py
```

The webcam will display predictions in real time.

---

## Technologies Used

* Python
* TensorFlow / Keras
* PyTorch
* Ultralytics YOLOv8
* OpenCV
* Streamlit

---

## Future Improvements

Possible extensions:

* Spider-Man object detection in scenes
* Multi-character detection
* Vision Transformer comparison
* Mobile deployment using TensorFlow Lite

---

## Author

**Bhuvan Mohan**

GitHub:
https://github.com/BhuvanMohan2005

---

## Acknowledgment

This project explores the use of **modern deep learning architectures for character classification** and demonstrates how such models can be deployed in real-world applications.

