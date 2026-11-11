
# 🌱 RootCause: Machine Learning for Crop Health

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?logo=tensorflow&logoColor=white)
![React Native](https://img.shields.io/badge/React_Native-61DAFB?logo=react&logoColor=black)
![Raspberry Pi](https://img.shields.io/badge/Raspberry_Pi-A22846?logo=raspberrypi&logoColor=white)
![Status](https://img.shields.io/badge/Status-Academic_Prototype-green)

## Project Overview

**RootCause** is an AI-powered crop disease detection system designed to help farmers identify plant diseases through image recognition.

The project combines **deep learning, computer vision, mobile application development, and edge computing** to provide accessible crop health assessments.

Using a **MobileNetV2-based Convolutional Neural Network (CNN)** trained on the PlantVillage dataset, RootCause classifies images of healthy and diseased plant leaves.

A React Native mobile application allows users to capture or upload plant images, which are processed through a Raspberry Pi-based edge computing system. The application returns disease predictions and confidence scores to support early detection and agricultural decision-making.

## Technologies Used

- **Programming:** Python, JavaScript
- **Deep Learning:** TensorFlow, Keras, MobileNetV2
- **Computer Vision:** CNN, Transfer Learning, Image Classification
- **Mobile Development:** React Native
- **Edge Computing:** Raspberry Pi, Kubernetes
- **System Integration:** REST API
- **Data Processing:** Image Resizing, Normalization, Data Augmentation
- **Model Evaluation:** Accuracy, Precision, Recall, F1-Score

## Dataset

The project uses the **PlantVillage dataset**, available on Kaggle, containing over 50,000 labeled images of healthy and diseased plant leaves.

**Data Preprocessing:**
- Resize images to 224 × 224 pixels
- Normalize image pixel values
- Apply data augmentation (rotation, flipping, shifting)
- Split dataset into 80% training and 20% validation

The model learns visual patterns associated with healthy plants and various crop diseases.

## Model Architecture

RootCause implements **MobileNetV2**, pretrained on ImageNet, using transfer learning to improve computational efficiency.

The model architecture includes:

1. MobileNetV2 pretrained feature extractor
2. Global Average Pooling layer
3. Dense layer with 128 neurons and ReLU activation
4. Dropout layer (0.3) to reduce overfitting
5. Softmax classification layer

**Training Configuration:**
- Optimizer: Adam
- Loss Function: Categorical Cross-Entropy
- Maximum Epochs: 20
- Early Stopping and Learning Rate Scheduling
- Fine-Tuning of upper MobileNetV2 layers

## System Architecture

RootCause integrates mobile and edge computing technologies through the following workflow:

1. **Image Capture:** Users take or upload a photograph of a plant leaf using the React Native application.
2. **Image Transmission:** The mobile application sends the image through a REST API.
3. **Model Inference:** A MobileNetV2 CNN hosted on a Raspberry Pi Kubernetes cluster processes the image.
4. **Disease Classification:** The model identifies potential crop diseases.
5. **Results Display:** The application displays the top three predictions with confidence scores.

This architecture separates the mobile interface from computationally intensive model inference.

## Model Performance

The MobileNetV2 model demonstrated substantial improvements during training.

| Evaluation Metric | Result |
|---|---|
| Initial Training Accuracy | 64% |
| Final Training Accuracy | 94.9% |
| Validation Accuracy | ~74–75% |
| Final Training Loss | 0.16 |
| Validation Loss | ~0.87–0.94 |

### Key Findings

- Training accuracy increased from 64% to 94.9%.
- Validation accuracy stabilized around 74–75%, indicating some overfitting.
- Tomato disease classes demonstrated relatively high precision but lower recall.
- Predictions for certain other crops showed inconsistent confidence levels.
- The model performed better under controlled dataset conditions than in variable real-world environments.

These results demonstrate the potential of transfer learning for crop disease classification while highlighting the importance of model generalization.

## Application Features

- Mobile-friendly React Native interface
- Camera-based plant image capture
- Image uploads from device storage
- AI-powered plant disease classification
- Top three predictions with confidence scores
- Raspberry Pi-based model inference
- REST API communication between mobile and edge devices

## Limitations

Several limitations were identified during development:

- Overfitting and limited generalization to real-world plant images
- Uneven model performance across crop categories
- Limited disease and plant species coverage
- Computational constraints of Raspberry Pi devices
- Sensitivity to lighting conditions, image quality, and background variations
- Dependence on connectivity between the mobile application and inference server

The current system serves as an academic prototype rather than a production-ready agricultural diagnostic solution.

## Future Improvements

Future development could focus on:

- Expanding training datasets with more diverse crop species and disease conditions
- Applying model compression and quantization for offline mobile inference
- Improving Raspberry Pi cluster performance
- Exploring cloud-based inference infrastructure
- Implementing image quality validation before classification
- Conducting real-world field testing
- Improving multilingual accessibility and mobile usability

## Conclusion

RootCause demonstrates the feasibility of combining **deep learning, mobile technology, and edge computing** to support automated crop disease detection.

Although the MobileNetV2 model achieved 94.9% training accuracy, its approximately 75% validation accuracy indicates that additional optimization and diverse training data are needed.

The project provides a foundation for developing accessible AI-powered agricultural tools that could help farmers identify crop diseases earlier and improve crop management practices.

## Project Team

**City University of Seattle**  
**DS510 – Artificial Intelligence for Data Science**  
School of Technology & Computing

**Team Members:**
- Hiromi Cota
- David Hiltzman
- Tung (Joseph) Tran

**Repository Maintainer:** [Joseph Tran](https://github.com/josephtrn01)

---

*An academic artificial intelligence project exploring deep learning, computer vision, and edge computing for accessible crop disease detection.*
