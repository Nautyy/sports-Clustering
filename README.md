# Image Clustering
Submitted by Ujjwal Narayan Pandram  
Roll No. IIT2021034  
College IIIT Allahabad  

---

## Table of Contents
1. [Problem Statement](#1-problem-statement)
2. [Methodology](#2-methodology)
   - [2.1 Initial Considerations](#21-initial-considerations)
   - [2.2 Transition to Clustering](#22-transition-to-clustering)
   - [2.3 Data Preparation](#23-data-preparation)
   - [2.4 Image Processing](#24-image-processing)
   - [2.5 Feature Extraction](#25-feature-extraction)
   - [2.6 Clustering and Classification](#26-clustering-and-classification)
   - [2.7 Court Image Segmentation (Future)](#27-court-image-segmentation-future)
3. [Execution Time](#3-execution-time)
4. [Results](#4-results)
5. [Conclusion](#5-conclusion)
6. [Future Work](#6-future-work)
7. [References](#7-references)
8. [Usage Note](#8-usage-note)

---

## 1. Problem Statement

The objective of this project is to classify images of badminton players into individual player classes using a dataset consisting of images from two folders one for players on the top half of the court and one for players on the bottom half. Additionally, a background image of the court is provided, which can be used to model the background color.

### Dataset Details
- TopTwoPlayers Contains images of the two players playing on the top half of the court.
- BottomTwoPlayers Contains images of the two players playing on the bottom half of the court.
- CourtImage The background image of the court, which assists in modeling the court’s color.

### Objective
The goal is to segregate the images into individual classes for four players, facilitating easier analysis of player performance and dynamics during matches.

---

## 2. Methodology

### 2.1 Initial Considerations
Upon analyzing the dataset, it became evident that there was no labeled data available for the players. Given this constraint, initial thoughts revolved around using a pre-trained model to classify the images directly. However, considering the absence of labeled data, traditional supervised learning methods were not applicable.

### 2.2 Transition to Clustering
Recognizing the unsupervised nature of the problem, the focus shifted towards employing clustering techniques. Clustering allows us to group similar images without the need for labels, thus facilitating the identification of distinct player classes based solely on the inherent characteristics of the images.

### 2.3 Data Preparation
- The dataset was organized into folders and uploaded into the working environment.
- The image files were extracted from a zip file, and paths to the images were established for processing.

### 2.4 Image Processing
- OpenCV was utilized for basic image processing tasks, such as reading, resizing, and saving images.
- Player images were preprocessed to ensure uniformity in dimensions and color scaling.

### 2.5 Feature Extraction
- ResNet50 A pre-trained ResNet50 model was employed for feature extraction from player images. The model was chosen for its efficiency and effectiveness in handling image data.
- The images were resized to (224, 224) pixels, suitable for input to the ResNet50 model, and preprocessed using `preprocess_input`.

### 2.6 Clustering and Classification
- KMeans Clustering KMeans clustering was applied to the extracted features, allowing for the categorization of images into four clusters representing the individual players. This approach leveraged the unsupervised learning paradigm effectively.
- Each cluster was associated with one player, and the images were saved into respective folders for each player.

### 2.7 Court Image Segmentation (Future)
- Image segmentation techniques were explored but not implemented in the final version. Future iterations may consider this to enhance the classification accuracy by focusing on player regions and minimizing background noise.

---

## 3. Execution Time
The total execution time of the implemented code was recorded, ensuring it did not exceed the specified limit of 2 minutes. The execution was efficient, with the image loading, processing, feature extraction, clustering, and saving of images all completed within the time constraints.

---

## 4. Results
The implementation successfully segregated the images into individual player classes. The results were organized in output folders as follows
- player_1 Contains images of Player 1.
- player_2 Contains images of Player 2.
- player_3 Contains images of Player 3.
- player_4 Contains images of Player 4.

### Sample Output Structure
The output folders provide a clear and organized structure for visual analysis, allowing for easy access to player images. Players are arranged as 1, 2, 3, 4 in order.

---

## 5. Conclusion
The project effectively demonstrated the application of computer vision and deep learning for classifying badminton player images. Utilizing ResNet50 for feature extraction and KMeans for clustering yielded a functional and efficient classification system, even in the absence of labeled data.

---

## 6. Future Work
- Enhancements in Clustering Future efforts may involve exploring different clustering algorithms or integrating advanced image segmentation techniques to refine the classification process.
- Real-Time Classification An avenue for exploration includes integrating this classification method with real-time image feeds during matches for dynamic analysis.

---

## 7. References
- Keras Documentation [Keras](httpskeras.io)
- Scikit-learn Documentation [Scikit-learn](httpsscikit-learn.orgstable)
- ResNet50 Research Paper Kaiming He et al., Deep Residual Learning for Image Recognition, 2015.

---

## 8. Usage Note
For an easier and more user-friendly experience, this project is implemented using Google Colab. You can find the Jupyter Notebook (`.ipynb` file) in the repository, which allows you to run the code without the need to manage environments and dependencies extensively.

---
