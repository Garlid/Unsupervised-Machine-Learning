## Auto MPG Project: PCA & T-SNE

The scenario for this project was to analyze data for a used automobile dealership in an effort to better understand different groupings of cars and how to more effectively target specific audiences. Due to the large volume of features in the data set, it was necessary to use dimensionality reduction techniques, such as Principal Component Analysis and T-Stochastic Neighbor Embedding. This project highlights my ability to utilize such techniques. 

---

### **Principal Component Analysis**
After scaling the data using the Standard Scaler, I used the sklearn library to import PCA. I created a PCA data frame, identified the percentage of variance explained by each principal component, and proceeded to plot the explained variances by components (see the *Explained Variances By Component* below). The least number of components that could explain more than 90% of the variation in the data was 3. After discovering this, I identified the principal components and visualized them in a data frame. I then used scatterplots to further visuzlize the principal components.   


**Explained Variances By Component**

![Explained Variances By Component](https://github.com/Garlid/Unsupervised-Machine-Learning/blob/main/Auto_MPG_Project/Principal_Component_Scatterplot.png)


**PC Dataframe**

![PC Dataframe](https://github.com/Garlid/Unsupervised-Machine-Learning/blob/main/Auto_MPG_Project/Principal_Component_Dataframe.png)



**PC Scatterplot**

![PC Scatterplot](https://github.com/Garlid/Unsupervised-Machine-Learning/blob/main/Auto_MPG_Project/Principal_Component_Scatterplot.png)

---

### **T-Stochastic Neighbor Embedding**
With t-SNE, I again used the scaled data I used for PCA. I chose to embed the data in a 2-dimensional space and proceeded to visualize the components in a scatterplot (see the *t-SNE Scatterplot* below). I used 3 clusters or groups and put those groups in boxplots to help visualize the variables in those groups. 



**t-SNE Scatterplot**

![t-SNE Scatterplot](https://github.com/Garlid/Unsupervised-Machine-Learning/blob/main/Auto_MPG_Project/t-SNE_Scatterplot.png)


**t-SNE Groupings Boxplots**

![t-SNE Groupings Boxplots](https://github.com/Garlid/Unsupervised-Machine-Learning/blob/main/Auto_MPG_Project/t-SNE_Boxplots.png)

### **Actionable Insights & Recommendations**

####**Observations**
There were three distinct groups of vehicles:
1. Light weight cars, few cylinders, higher MPG, and newest model year (likely sedans)
2. Heavy-eight vehicles, higher horsepower, slower accelerations (likely trucks)
3. "Goldy-locks" cars that are not too heavy nor too light, medium MPG, medium horsepower, and moderate accelaration

####**Recommendations**
1. The largest group of cars are the newer models with better MPG. My first recommendation would be to increase stock of these vehicles. In this changing environment with shifting market conditions, globalization and cost pressure impacting most industries, the target market will likley be seeking vehicles that have better gas mileage.
2. The second largest group contains vehicles with more hauling power and lower gas mileage. This sort of vehicle (likely trucks) appeal to a separate group of customers who may be less interested in saving gas money and more interested in the vehicle's abilities to haul effectively. This cluster is smaller than the first, so SecondLife ought to keep a good selection on hand, but perhaps not as many as the first group or cluster.
3. The smallest group are those with some hauling power, variable MPG, and medium acceleration. Keeping a few of these types of vehicles in stock (but not too many) will appeal to a third customer-type.
