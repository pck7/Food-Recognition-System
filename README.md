# Spots Nutrition Tracking  

**Author**: Piyush Chanduka  
**Institution**: BITS Pilani, Pilani Campus  

---

## Introduction  

**Spots Nutrition Tracking** is a deep learning-based project designed to assist athletes and health-conscious individuals in maintaining optimal nutrition and performance. By leveraging computer vision and neural networks, the project classifies food items, estimates their calorie content, and provides personalized nutritional insights.  

The project aims to:  
- Develop a food recognition system.  
- Implement a robust calorie estimation method.  

---

## Problem Statement  

Given a set of food images, the project focuses on:  
1. Detecting the type of food using Convolutional Neural Networks (CNN).  
2. Estimating the weight and calorie content of food items.  
3. Providing a personalized application for users.  
4. Addressing overlapping food items for accurate calorie estimation (future objective).  

---

## Dataset  

The project utilizes the **FOODD dataset**, which comprises diverse food images captured under varying conditions. The dataset is categorized based on:  
- **Devices**: Samsung-S4, iOS-4, CanonSD1400  
- **Lighting Conditions**: Light and Dark environments  

Food items analyzed:  
- Apple, Orange, Banana, Tomato, Onion, Cucumber, Carrot  

---

## Methodology  

### Food Recognition Model  

The food recognition model uses a Convolutional Neural Network (CNN) with the following architecture:  
- **5 Convolutional Layers** with ReLU activations.  
- **Dropout Layers** to reduce overfitting.  
- **SoftMax Layer** for classification.  

#### Training Details  
- **Dataset**: 100 images per category, resized to 300x300 pixels.  
- **Optimizer**: Adam  
- **Loss Function**: Categorical Cross-Entropy  
- **Learning Rate**: 0.0001  
- **Training Accuracy**: **86.06%**  
- **Total Loss**: **1.11**  

### Calorie Estimation  

The calorie estimation process involves:  
1. **Image Segmentation** to extract food pixels and reference object pixels (thumb size).  
2. **Pixel-to-CM Multiplier** calculation.  
3. **Volume Estimation** based on the shape of food items:  
   - **Sphere** (e.g., apple, orange):  
     \[
     Volume = \frac{4}{3} \pi (Estimated\_Radius)^3
     \]  
   - **Cylinder** (e.g., banana, cucumber):  
     \[
     Volume = \pi (Estimated\_Height) (Estimated\_Radius)^2
     \]  
4. **Weight and Calories** estimation:  
   \[
   Weight = Density \times Volume
   \]  
   \[
   Calories = \frac{Weight \times Calories\_per\_100g}{100}
   \]  

---

## Implementation  

### Achieved Objectives  
- Food recognition and calorie estimation (Objectives 1 and 2).  
- Partial implementation of personalized application (Objective 3).  

### Limitations  
- Overlapping food estimation (Objective 4) needs further research.  
- The personalized user interface requires a labeled dataset.  

---

## Code  

The implementation code is hosted on **Google Colab**.  
You can access it here: [Google Colab Link](https://colab.research.google.com/drive/1ypUrp91iyDbqOO7hNWUMzvKzBieJ4Fm4)  

---

## References  

1. [Mask R-CNN Overview](https://viso.ai/deep-learning/mask-r-cnn/)  
2. [Food Calorie Estimation Using Image Processing](https://github.com/vinayaksable2399/Food-Calories-Estimation-Using-Image-Processing)  
3. P. Pouladzadeh et al., *Measuring Calorie and Nutrition from Food Image*, IEEE Transactions on Instrumentation & Measurement, 2014.  
4. P. Pouladzadeh et al., *FOODD Dataset for Calorie Measurement*, International Conference on Multimedia Assisted Dietary Management, 2015.  
5. Meghana M Reddy, *Calorie Estimation from Food Images using OpenCV*, GitHub, 2016.  

---

## Future Work  

- Enhance the dataset with more labeled samples for improved accuracy.  
- Develop solutions for overlapping food estimation challenges.  
- Build a fully functional personalized user interface.  

