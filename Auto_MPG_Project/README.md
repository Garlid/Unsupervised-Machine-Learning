## Auto MPG Project: PCA & T-SNE

The scenario for this project was to analyze data for a used automobile dealership in an effort to better understand different groupings of cars and how to more effectively target specific audiences. Due to the large volume of features in the data set, it was necessary to use dimensionality reduction techniques, such as Principal Component Analysis and T-Stochastic Neighbor Embedding. This project highlights my ability to utilize such techniques. 

---

### **Principal Component Analysis**
After scaling the data using the Standard Scaler, I used the sklearn library to import PCA. I created a PCA data frame, identified the percentage of variance explained by each principal component, and proceeded to plot the explained variances by components (see the *Explained Variances By Component* below). The least number of components that could explain more than 90% of the variation in the data was 3. After discovering this, I identified the principal components and visualized them in a data frame. I then used scatterplots to further visuzlize the principal components.   

---

### **T-Stochastic Neighbor Embedding**
With t-SNE, I again used the scaled data I used for PCA. I chose to embed the data in a 2-dimensional space and proceeded to visualize the components in a scatterplot (see the *t-SNE Scatterplot* below). 


