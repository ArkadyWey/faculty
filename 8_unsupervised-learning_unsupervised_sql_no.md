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
- We would like to get the data to a number of dimensions that we can visualise  
- We should think of dimensionality reduction as a method of projecting onto a lower dimensional space. 


Why is it needed?
- Features arae highly correlated so don't need them all 
- Manual feature slection is often very difficult : i.e. picking out wjhich features are similar to other features 
- Clusterning is hard in higih dimensiional space

Curse of dimensionalaity
- In 1-D, let's say data occupies 1/10th of space. Then in d-D, data occupies (1/10)^d of space. 

Applications 
- Feature selection : get optimal subset of features
- Feature extraction : project whole data set into lower dimensional space 
- Visualisation : Want to be able to show client 
- Increasing speed : In other algorithms we want to use

### Linear dimensionality reduction - PCA (Principal Component Analysis)

- Choose another basis for thee data space
- Find orthogonal axes of higheest variance via an eigenvalue decomposition
- I.e. find the eigenvector directions that have the largest eigenvalues

How many principle components to retain?
- Plot variance retained vs number of dimensions 
- Our aim is to decrease dimensions as much as possible without losing too much variance 
- We usually want to decrease to two or three dimensions for visualisation, for example, to spot a linear relationship. 

Example 
- MNIST data set 
- Forget the lable and use dimension reduction 
- Starts with with dimension 28*28=784 dimensional image so space is 784 pixel brightnesses to choose so this is the dimenension of the space
- We use PCA to reduce this number to two and we observe points that are loosely cliustered based on their number. 
- We then give this to k means that clusters but these clusters don't really correspond to numbers 

### Non-linear dimensionality reductions

#### SNE and t-SNE 
Stochastic neighbourhood embedding and t-distributed stochastic neighbourhood embedding 

- On the higher dimensional space, construct conditional distributionon one point givien another point.  
- One the lower dimensional space, construct another distriibution on a random set of points. 
In t-*, we use the t-student distribution. 
- Move the lower dimensional doistribution to optimise the Kullbacl-LEibler function via gradient descent.  

### UMAP 
Uniform Manifold Approximation and Projection 

- 'The most mathematically complicated idea in machine learning' 
- See the readthedocs on the algorithm. 
- Amazing algorithm - read about it.

### Autoencoders 

- Can we compress our data to a subset where we haven't lost much information?
- We use a funnel shaped neural network to encode and opposite shaped funnel to decode 
- We train the encoder and decoder to make the input and output the same. 
- So the network is forced to learn how to compress data because the less lossy we can make the compression teh better we can construct the data on the other side. 
- If you check away the decoder, the encoder gives a method for taking ahigh dimiensional vector and spitting out a low dimensional vector.

- When activiation functions are linear, optimal encoding is just PCA 

### Summary 

#### Clustering 
- Find struvture ini unlabelled data 
- Understand what clusters are 

#### Dimensionality reduction 
- Visualisiation 
- Tradeoff between linear and non-linear 

START WITH UMAP AND HDBSCAN




