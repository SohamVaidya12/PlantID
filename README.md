<div align="center">
  <img src="Leafid12.jpg" alt="LEAFID" width="40%">
</div>

# LeafID: ML-Based Leaf Identification System  

**LeafID** is a robust and interactive system designed to classify leaves in real-time using a pre-trained machine learning model. It provides accurate identification of leaf types while supporting live webcam feed processing and PDF report generation.

---

## 🚀 Project Overview  

- **Frontend**: Built with Gradio for an intuitive user interface, enabling users to upload images for classification.  
- **Backend**: Implements OpenCV for image processing, integrates a pre-trained model from Teachable Machine, and supports real-time detection using a webcam feed.  
- **Dataset**: Utilizes a licensed dataset trained on Teachable Machine for Hibiscus and Guava leaf classification.  

---

## 🌟 Key Features

- **Real-Time Detection**: Seamlessly detects and analyzes leaves using a live webcam feed or uploaded images.  
- **AI-Driven Classification**: Powered by a pre-trained model developed with **Teachable Machine**.  
- **Detailed Reporting**: Automatically generates downloadable PDF reports for each classification.  
- **Optimized Leaf Detection**: Tailored HSV color filtering ensures accurate leaf isolation, even in varying lighting conditions.
  
---

## 🔍 Workflow  

### **1. Data Collection and Model Training**
- Gathered images of Hibiscus and Guava leaves.
- Collected them in the folders and applied augmentation.
- Trained a custom ML model using **Google's Teachable Machine** to classify the two types of leaves.
- Exported the trained model in TensorFlow Lite format (`keras_model.h5`) with labels (`labels.txt`).

### **2. Backend Image Processing**
- Initialized a webcam feed using OpenCV for real-time leaf detection.
- Processed the image frames to isolate leaves based on their green color using HSV color masking.
- Detected the largest contour in the processed mask to identify the leaf region.
- Resized the detected leaf to a standard dimension (300x300 pixels) for model compatibility.

### **3. Classification with Pre-Trained Model**
- Integrated the Teachable Machine model for classification using the `cvzone.ClassificationModule`.
- Used a confidence threshold of 50% to filter predictions.
- Labeled the detected leaf as **Hibiscus leaf** or **Guava leaf** with the confidence percentage.

### **4. User Interaction and Output**
- Provided a **Gradio Interface** for image uploads, classification, and PDF report generation.
- Displayed real-time classification results with bounding boxes and labels using the webcam feed.
- Generated detailed PDF reports summarizing the classification results.

---

## Backend Overview

The backend of the "LeafID" system utilizes a pretrained machine learning model for real-time classification of leaf types using a webcam. It focuses on identifying **Hibiscus** and **Guava** leaves.

### Key Features:
- **Leaf Detection**: Uses OpenCV to capture and process the webcam feed.
- **Contour Detection**: Isolates the largest contour, assumed to be the leaf.
- **Pretrained Model**: Trained with **Teachable Machine** for Hibiscus and Guava leaf classification.
- **Real-Time Prediction**: Displays the classified leaf type with a confidence score.

### Process:
1. Capture the webcam feed.
2. Process and isolate the leaf using color filtering and contour detection.
3. Classify the leaf using the pretrained model.
4. Display the classification result on the video feed.

### Libraries and Tools Used:
- **OpenCV** for image processing.
- **cvzone** for model classification.
- **Teachable Machine** for the custom model.



### Interactive Video Demonstration:

Click the button below to watch the backend in action :

[Watch the Backend in Action](PlantID.mp4)🎥

Alternatively, you can view the video directly below:

<video width="100%" controls>
  <source src="PlantID.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

---

## Frontend: Gradio Interface for LeafID

The **LeafID** frontend uses **Gradio** to create an intuitive user interface for leaf classification. Users can upload leaf images to be classified as either **Hibiscus** or **Guava**. The interface also allows users to download a detailed PDF report for each classification.

### 🎥 User Interface Flow

1. **Upload Leaf Image**  
   Users upload an image of a leaf (e.g., Hibiscus or Guava).
   - The uploaded image is processed by OpenCV and the pre-trained model.

2. **Leaf Classification**  
   The uploaded image is processed for **leaf detection**, and classification is performed using the pre-trained model.
   - **Leaf Type**: Either **Hibiscus leaf** or **Guava leaf**.
   - **Confidence (%)**: The confidence of the classification result.
   - **Description**: A brief description of the classified leaf.

3. **Download PDF Report**  
   A PDF report is generated, summarizing:
   - Leaf type
   - Confidence score
   - Description
   - The report can be downloaded for further analysis.
     
<div style="display: flex; justify-content: space-between; align-items: center; gap: 20px;">

  <img src="f1.png" width="70%" style="object-fit: contain;">
  <img src="frontend_img2.png" width="70%" style="object-fit: contain;">

</div>





---
## 📊 Observations

### Model Performance
- **Confidence Score Range**: 98% - 99% for both Hibiscus and Guava leaf classifications.
- The default threshold for classification is set to 50%, but the model's confidence score is consistently higher.
- **Hibiscus Leaf Confidence**: 98.5% - 99.2%
- **Guava Leaf Confidence**: 98.0% - 99.1%

---

## Conclusion

The model performs with exceptional accuracy, achieving 98% - 99% confidence in classifying Hibiscus and Guava leaves. Despite the default classification threshold being set at 50%, the high confidence range assures reliable and accurate predictions, making **LeafID** a highly effective solution for real-time leaf identification.

 











