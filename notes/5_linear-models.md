# Day 5 

## Linear algorithms 
David Peinador Veiga

### Introduction 

Context: Supervised learning 
- Task of learninig a function that maps set of features to target variable 
- Done based on set of labelled variables 
- Done by tuning a set of variables

Components of supervised learning algorithm 
- Model - functional form that contains paramters to learn 
- Losss function  - how we assess if output is right or wrong 
- OPtiisation algorithm - updates parameters 
- Evaluation strateegy - Says whether trained model is good or not

Regression 
- Trying to estimate continuous target e.g. prie of stock

Classification 
- Classifying discrete features into catagories  

- NB: There are not the only two : e.g. named entity recognition 

Notation 
- Greek letter for feature index - so 3 featuers then alpha runs from 1 to 3
- Latin index for sample 
- x_alpha are random variables 
- x_alpha,i are samples that we will actualy use - this is a matrix of sampled values
- parameeters are \theta
- y_i vector of samples target

Linear algorithms
- The model function has to be linear on the PARAMETERS NOT THE FEATURES 
- This requires important assumptions: 
- Linear independence between features 
- Significance of each feature value grows linearly -- if a feature doubles, its weifht in the preduiction doubles as well 
- Contributions of each feature to the predictiona are independent of each other

Features and variables 
- Variable is the data itself - e.g. salary 
- Feature is any derivative of the variable - e.g. log of the salary 
- Note that x are features, not variables

Why linear models?
- Simple but work well - good benchmmark 
- Explainable 
- Building blocks of other models 

### Linear regressiosn 
Functional form 
$$f(x_\alpha,\theta_\alpha) = \theta_0 + \sum_{i=1}^m x_i \theta_i$$

Nothing prevents us from going non-linear in features. 
- We only need to be linear in parameters. 
- Can take mnonliner functiono of features 
- For example, polynomial regression
$$f(x_\alpha,\theta_\alpha) = \theta_0 + \sum_{\alpha=1}^m (x_i)^i \theta_i$$
- Note that features can be dependent but NOT LINEARLY DEPENDENT. 

Loss function
- We would like to minimise difference between prediction and target 
$$\epsilon_i = y_i - f(x_{\alpha,i},\theta_\alpha)$$
- There are different types of loss function. 
- MSE corresponds to normally distributed error 
- MAE coresponds to Laplce distirbuted error 

Bayesian perpsecgive 
- We know the probability pf data given parameters - likelihood 
- Know probaility of parameters - prior
- Know probailtiy of  data 
- We don't know prob of parameters given data - posterior
- But maximising posterior looks like minimisinig MSE 

Optimisation 
- For linear regression, optimisation is done analytically when we use the MSE AS LOSS FUNCTION
- We get the derivatiive, set it to zero, and find $\theta$ explicitly. 

- For lienar regression with MAE, we cannot use explicit solution because not differentialbel 
- So use gradient descent
- Take local graident of loss function and step in that direction 
- Size of step is called leaernnig rate -- if this is too low we might not reach the minimum, if this is too high, we go from one side of the minimum to the other.

- There are other methods such as stochastic gradient descent. 
- This is where we take a direction randomly, find the gradient in that direction, and then take a step. 
- That is, we replace the gradient by an approximation of the gradient. 

Evaluation 
- Can use root MSE, MAE, coefficient R^2 
- Use these to asset whether underfitting or overfitting 

Regularisation 
- Method to avoidi overfitting 
- This is addinig another term to the loss to contrain it 
- Common regulsriased loss functions are Ridge regression, LASSO regression, and Elastic Net Regression
- These prevent the parameters from getting too large. 
- This is based on the belief that one parameter should not be too large because this is unlikely.
- Choosing large lambda cprresponds to assumign that parameters shjould be very small.

Advanatages 
- Ridge - L2 - differentialbe but shrinks parameters but never makes them zero 
- LASSO - L1 - nondifferentible but shrinks paramesterrs and makes some zero 

### Logistic regression 
Functional form 

- If we just use regression, then end up with a line when we really want 1 or 0 
- Solution is to use sugmoid which maps real line to numbers between 0 and 1 
- Let p be prob that outcome is 1. 
- Then log of odds is linear  

$$logit(p)=log(p/1-p)= \theta_0 + \sum_{\alpha=1}^m \theta_\alpha x_\alpha$$

- We can also go non-linear in the features as before 
- For example, polynomial logistic regression 

Multisclass 
- Use softmax instead of sigmoid

Loss function 

Evaluation 
- Choose a metric that makes sense in your problem 


### Other models 

## Computational statistics 
Arnaud Leredde  

Goals 
- Sampling distributions 
- Understand bootstrapping and useit to estimate uncertainty in parmeters of interest

### Sampling distributions 
- You have a data set that is sampled a larger population that follows some distribution 
- You compute a statistic of interest from this dataset
- If this data set is large enough, we can expect that ti is similar to that of the larger population (called teh tru valuee)
- But how close is close?

- If we took another sample of the population, theen our statistic would change
- How much would it change by?

Threee thigns matter 
- The size of the underlying data set 
- The size of the sample data set
- The statistic that we wish to compute

Empirical distribution 
- We take a random data set 
- Compute the mean 
- Repeat 
- The distribution of these means is called thee empirical dsitribution

- Mean of the red curve tends to mean of the sampling distribution 

So...
- Statistic has its own distribution 
- Number of samples affects deviation of empirical distribution
- Most empirical distirbutions are normal... i.e. the distirbutio of sampled means is normal 
- For some statistics this can be proved asynmptotcally 
- However, this is hard for more complex distributions 
 
Recap 
- Statisics inherit a distribution called smapling distribution 
- The mean of 10 data points and mean of 100 points count as differetn statistics becasue htey will have a different distribution 
- If we knew the sampling distribution, we woulc compute confidence intervals

### Boostrapping 
- The data we have gives us an empirical probability distribution. 
- Plug in pricipal - substitute dataset for empirical data set (i.e. assume empirical data set full represents tru ddata set )

- Pick points with probability defined by pdf - gives samples distribution -- these are called boostrapped distributions (these are the same size as the original data set)
- For each of these, calculate the mean 
- Put these means into a histogram 
- This has the same shape as the original distribution but its centre is different 
- This is because the original data set has a mean that is not the same as that of the true population 

- So the mean of the popukation is the mean of the sample that we took 
- The error on this mean is given by the stadard deviation of the bootstrapped histogram 

- So we can use this bootstrapped histogram to estimate the error in almost any statistic of the sampled distribution

## 3. Presenting 
Maria Diaz 

- Hiring and job plan - better candidate to get the right job
- Communications work plan - become an effective communicator 

- Week 1 - careers 
- Week 2 - communicating at the right level 
- WEek 3 
- Week 4 - CVs and Bios workshops ... 

### How to structure a presentation 

Avoid big mistakes 
- Too much texts 
- Small font 
- Reading from the slide 
- Lack of energy 
- Of course everyone knows...
- Too technical for audience 
- No clear point 
- No audience benefit 
- No clear flow -- not sure where it's going
- Too detailed
- Too long
- Don't force people to think... YOU tell the story

Find the right message 
- Take the audience from A to B
- What does the aiidience want - learning / entertainment / inspiring / impact 
- Serve the audience interest 
- Knowledge level of the audience 
- Identity of the audience - what are their roles
- Conection with them from what you're talking about 
- Improving their own skills 
- Making money
- Gaining power
- Fame 
- Sex
- Trancendance - help otehrs to realise their potential 
- Self actualisation - realising our own potential 
- Aesthetic - order, beauty, balance 
- Lerning - understand 
- Esteem - be competent, get approval 
- Belonging - love / family / friends 

Develop the content 

Find a structure 
- Rhetorical questions 
- Look at Visme / Duarte / Forbes

Figure out the opening 
- Grab interest 
- Unique selling point 
- Simple concrete validation 


... just like writing a journal article 










 


