
Instructions for executing this code:

To execute this code, you have two options:

Download the code as a zip file from the GitHub repository:

Extract the zip file's contents to a directory on your local machine.
Clone the code using Git:

Open a terminal or command prompt on your machine.
Run the command: git clone https://github.com/VenkatakrishnaManne8/Clustering-Single-Cell-RNA-Sequencing.git
Once you have the code on your machine, follow the specific instructions based on the code editor you are using:

For Visual Studio Code (VScode):

Open the code files in VScode.
Update the file locations or paths of the train and test data within the code (Lines 15, 19) to match their location on your machine.
After updating the file locations, run the code using the command: py Dmml-final-code.py
For Jupyter Notebook:

Launch Jupyter Notebook on your system.
Open the downloaded source code file from the GitHub repository.
Update the path for the train and test data sets in the code to match their current location on your machine.
Save the code.
Run the code in the Jupyter Notebook environment.
Introduction: The challenge is to cluster the data into 16 clusters using a single-cell RNA Sequencing dataset. Single-cell RNA sequencing (scRNA-seq) is a powerful technique for analyzing the whole transcriptome of individual cells, and the goal is to develop machine learning models or strategies for detecting cell accuracy.

Data Preparation:

Feature Selection:

Variance Threshold: This technique eliminates constant or zero variance features within the dataset. After exploring the data, it was found that many features have a lot of zeroes or almost zero variance, which doesn't contribute to the model's understanding of the data and may not yield good results. A threshold value of 0.005 was set, resulting in the removal of 3029 features. Removing these low variance features improved accuracy.

Scaling: After feature selection, the data is scaled using the standard scaler, which standardizes the data to have a mean of 0 and a standard deviation of 1 across each feature.

Dimensionality Reduction: PCA: Since the dataset is high-dimensional, Principal Component Analysis (PCA) is applied as a linear technique to obtain orthogonal transformations of the dataset, selecting the principal components that retain most of the variance while reducing dimensions. 50 principal components were taken in the final model, accounting for around 94.5% of the variance, which helped train the model faster and achieve higher accuracy.

Model Training:

For model training, various models were explored to achieve better accuracy. The chosen model for this competition is Birch, a clustering algorithm suitable for large datasets, as it efficiently summarizes the data into small clusters without losing much information. The Birch model achieved an accuracy of 88.53 on the training dataset and 89.12 on the test dataset.

K-means: K-means was also tried with different techniques to improve accuracy. By applying feature selection with PCA and standard scaling, the K-means model achieved a silhouette score of 0.0013 and an accuracy of 81.24.

Agglomerative: Another approach using Agglomerative clustering with feature selection and standard scaling achieved a silhouette score of 0.0046 and an accuracy of 83.64.

Birch: A third approach with Birch clustering, feature selection, and PCA achieved the highest accuracy of 88.53 with a silhouette score of 0.0067.

Internal Evaluation: Silhouette score was used for internal evaluation, ranging from -1 to 1, indicating the quality of clustering. The final silhouette score achieved for the training data was 0.0067, and for the test data, it was 0.011.
