## Auto MPG Project: PCA & T-SNE

The scenario for this project was to analyze data for a used automobile dealership in an effort to better understand different groupings of cars and how to more effectively target specific audiences. Due to the large volume of features in the data set, it was necessary to use dimensionality reduction techniques, such as Principal Component Analysis and T-Stochastic Neighbor Embedding. This project highlights my ability to utilize such techniques. 

---

### **Principal Component Analysis**
After scaling the data using the Standard Scaler, I used the sklearn library to import PCA. I created a PCA data frame, identified the percentage of variance explained by each principal component, and proceeded to plot the explained variances by components (see the *Explained Variances By Component* below). The least number of components that could explain more than 90% of the variation in the data was 3. After discovering this, I identified the principal components and visualized them in a data frame. I then used scatterplots to further visuzlize the principal components.   

---

### **Skills Demonstrated**
- **Data Preprocessing**: Handling and cleaning large datasets.
- **Exploratory Data Analysis (EDA)**: Gaining insights from raw data and preparing it for clustering.
- **Clustering Evaluation**: Using metrics such as **silhouette scores** to assess the performance of different algorithms.
- **Outlier Handling**: Identifying and mitigating the impact of outliers on clustering results.
- **Principal Component Analysis**: Condensing data down so it can be visualized as either 2D or 3D data
- **T-Stochastic Neighbor Embedding**: 

---

### **Projects Overview**
#### 1. **Auto MPG**
The first project in this repository is a project from MIT's **Data Science and Machine Learning Program**. The project utilized T-SNE and PCA in order to reduce dimensionality of the data and extract insights.

#### 2. **Market Segmentation with K-Medoids (MIT Capstone)**
The second project in this repository is my capstone project from MIT's **Data Science and Machine Learning Program**. After evaluating multiple clustering algorithms, I selected **K-Medoids** as the most appropriate for the dataset due to its:
- High **silhouette score**, indicating compact and well-separated clusters.
- Robustness against **outliers**, which was crucial for this dataset.

The project includes:
- Raw data
- Preprocessed and analyzed data
- Code for clustering and evaluation
- Final presentation delivered on December 13, 2023

**Details of this project can be found in the** [Market_Segmentation_With_K-Medoids folder](https://github.com/Garlid/Unsupervised-Machine-Learning/tree/main/Market_Segmentation_With_K-Medoids).

---

### **Future Additions**
I plan to expand this repository with more clustering projects, exploring real-world datasets and advanced evaluation techniques.

---

### Notes
- This repository highlights my technical skills in **unsupervised learning** and the ability to communicate results effectively to both technical and non-technical audiences.
- Each subfolder contains a `README.md` with specific details about the corresponding project.

---

### **How to Use This Repository**
1. Navigate to the folders listed above for each project.
2. Explore the notebooks, datasets, and visualizations within each subfolder.

---
