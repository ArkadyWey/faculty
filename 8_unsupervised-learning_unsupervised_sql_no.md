# Day 8 

## Unsupervised learning  
Chris Evans and Nonie Alexander 

Supervised 
- Access to target variabl 
- E.g. regressiona and classification  

Unsupervised 
- No access to target variables

### Clustering overview
- K means 
- Hierarchical 
- DBSCAM 
- HDBSCAN 
- Pipeline 

### Clustering 
- Finding groups of data that share ore characteristiics that those in other groups  
- Detect stucture 

Issues 
- What does similar mean?
- There aren't always clusters 
- How do you know you're right when data is unlabelled?

### Applications of clustering  
- Marketing : identifying people who are simiilar customers 
- Image : Similar pixels 
- Natural language : topic analysis -- need to vectorise sentences?! 

### Defining similarity 
- Pictures that look similar might not have similiar contents 
- We need to define smilarity mathematically 

### k-means 
- Flat clusters 
- Model parameter is number of clusters and distance metric 

- Define number of clusters 
- Minimise distance from centroid to each data point 
- Put two centroids randomly in space of data 

Finding k 
- Repeat for a range of k 
- Select optimal k based on clustering method 

Basic method - elbow plot 
- Plot in group sum of squares for each k
- Find the elbow
- Problems are might not be elbow, might be more than one

Other methods
- Silhouette method : measure how mjuch each point belongs to each cluster (between -1 and 1)
- Gap statistic : calculates  cluster dispersion compared to some metric 

Distance metric 
- Use Euclidean
- Manhattan 
- Hamming 
- Cosine 

Assumptions 
- Clusters are spherical 
- They are linearly separable 
- Every point belongs to a cluster 

Disadvantvages 
- Local minima prevent optimal cluster 
- Sensitive to inital partition 

### Hierarchical clustering 
- Call every point to be a cluster 
- Let two points closest to eaach other to be a cluster 
- Repeat until only one cluster remains 

What is distance between clusters?
- Min : closest two points in different clusters
- Max : ditto but furthest
- Average : ditto but average 

### DBSCAN 
Density Based Spatial Clusterning of Applications with Noise 

- Clusters regions of high point density 
- Identifies noise and outliers 

Different types of points 
- Core point : there are more than a certain number of points in its neighbourhood 
- Boundary points : don't have that many ;oints in their neighbourhoodd but near a core 
- Outlier : don't satisfy other things 

- Pick a point 
- idientify it as the type of point

- How do you choose min points to be called acore? 
- How dod you choose the radius of the sphere?

ADvantages 
- Takes noise into account 
- Takes irregularly shaped cluseters into account  

Disadvantages 
- Parameters are not inituitive - hard to fine tune  
- Assumes uniform density 

### HDBSCAN 
Hierarchical Density Based Spatial Clusterning of Applications with Noise 

- This is better because it accounts for non-uniform density 

- Complex methods - view the readthedocs for explanation. 

### Evaluation 
- How do we evaluate when we don't know labels? 
- Use internal and external evaluation
- Internal is looking at clusters independently of domain knowledge. This involves picking the right metric for the right data. 
- Reproducable : If you perform cluster method on a slightly differet daata set, do the same clusters appear?
- Predicitiive : Do the results predict an outcome that isi tangiible? : Do the dat points in a particular cluster beshave in a certain way? 
- Do they cluster groupings make sense in the context of the subject matter? 

### Closing thoughts
- Easy to do, hard to do well
- More that we haven't talked about : spectral clustering / Gaussian mixtures
- Might not need to do it - can we use semi-supervised methods?

### Dimensionality reduction 

