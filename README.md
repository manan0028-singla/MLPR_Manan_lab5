# MLPR_Manan_lab5
Aim 
The goal of this lab is to locate human faces in an image, identify their key characteristics, and group similar-looking faces using unsupervised machine learning. It shows how computer vision and clustering can work together to organize facial data automatically without needing any prior labels or categories.

Methodology
The project is organized into four distinct steps:
1. Face Detection We use the OpenCV Haar Cascade Classifier to locate faces in an image. The photo is turned into grayscale first to make the detection process faster and more accurate.
    * Visual: Boxes are drawn around the detected faces.
2. Feature Extraction Each face is converted from standard color (BGR) to HSV (Hue, Saturation, Value). We then calculate the average Hue and Saturation for each face, creating a simple numerical "fingerprint" of its color.
    * Visual: Individual cropped faces are shown for analysis.
3. K-Means Clustering Using the K-Means algorithm (with $k=2$), we group the faces based on their color features. Since this is unsupervised, the computer finds patterns on its own without being told who the faces belong to.
    * Visual: A scatter plot shows the two groups and their center points (centroids).
4. Testing a New Face A new "template" face goes through the same detection and feature steps. The trained model then assigns it to the group it matches most closely based on its distance from the cluster centers.
    * Visual: The new face is added to the scatter plot to show which group it joined.

Key Findings
* Haar Cascades are reliable for picking out several faces at once.
* HSV values work well as a simple way to represent and group facial data.
* K-Means successfully organizes faces by visual style without needing labels.
* The model can easily categorize unseen faces once the clusters are established.

Conclusion
This lab shows how to build a full system that combines computer vision and unsupervised learning. While this method groups faces by look rather than identifying specific people, it proves how important feature selection is in machine learning.
Limitations:
* Changes in lighting can mess up the clustering.
* Color alone isn't enough for high-level facial recognition.
* You have to manually decide how many groups ($k$) to create.
* Future Fixes: Using texture details or deep learning "embeddings" would make the system much more accurate.
