# Bagging and boosting 
Ryan Hannam

## Overview 
- These are methods of ensembling machine learning models to make better ones. 
- Decision trees being used in a random forest is the classical example. 
- While LLMs and transformers are useful, when it comes to tabular data, then tree based methods are still king in terms of their predictive power. They outperform neural nets.

## Trees 
- Aim is to split data on a rule and gaiini information.
- Problem is that as the treee grows the data pool on each branch gets smaler so less statistically significiant.
- In other words, we have lost information about what is common in different groups. 

## Ensembling decisiion trees 
- Note that when we are leaerning from data, we are learning from signal but also noise. 
- This is done even when a model is quite simple. 
- Therefore, when models get too complex we are learning from noise.
- Therefore, very complicated decision trees just contain one data point in each leaf node and are overfitted.
- Bagging and boosting is a way of preventing overfitting. 

## Bagging 

### Intuitition
- All models overfiit but ooverfitr in different ways 
- Bagging is using models together and hope that the learning from noise cancels out.
- Example isdoctor that has had a bad experienc and so recommends intrusive prociiedure when not needed.
- If you add a lot of docts with different bad experience then these cancel out. 

### Bagging - Bootstrap aggregating 
- Take a data set 
- Sample data with replacement to make a new data set of same size(boostrapping)
- Repeat this a number of times 
- Train a model on each data set 
- Prediction of overall models is a average /combination (aggregate) of those models.

### Why bag decision trees?
- Decision tree is highly variable.
- Botostrap sample can be sensitiive to first split. 
- Decision trees are greedy learners - so when we take a bootstrap data set they get more senstive to first split. Therefore random forest tends to be bettter at lower depths.
- Decision trees are not analysitc so can't do anything bayesian. 

### Bagging doesn't always reduce variance
- Might be one feature that is so important that one feature always gets descriminiatein firist split. 
- This means that trees will all be corrrelated . 
- To overcome this we need random feature selection. 

- At each node, we sample a selection of the features to make the choice of spliit on.
- Before, we looked at all features and saw which gave the greatest information gan. 
- Think of asking who likes video games - age is going to be more important.
- This is an imoportant feature, but we want to avoid it because we want to check if there are other important features.
- This avoide missing other important features that might become more important if there is darta drift (foro example if the gaming insudtry changes its target market).

### Random forests in practice 
- Used to be first choice, now they're secodn to XGBoost.
- Forests are scalable because can put each one on different cpu. 
- Perform better than decision trees but not crazily better. 

## Boosting 

The rough idea is...
- Train adoctor to make a diagnosis 
- Second doctor is trained to spot the errors that the doctor makes. 
- You could then have a third doctor spotting the mistakes of thes econd one... etc..
- So rather than training models at the same time, you train them sequentially.

### Boosting examples  

#### Water 
- Areas are bofrken down into awter areas 
- Tehy have data about water consumption. 
- Want to preduct how much consumption would be used so they know how much piping to build in that area. 

- A large parat of this problem is linear - water is proportional to number of properties in that area.
- But what about nonlinear relationships - difference begween 4 bed and 19 bed house might be different

- If we were bagging, trhen we would just train multiple trees and take the average. 


### Boosting decision trees as a regressor/classifier 

#### Why would be boost one?
- Same reason as bagging - want more info without overfitting.

#### Regression 

- Have loss function to minimise 
- We train a first one
- Plug residual of first tree into the loss function of the second tree.
- Aand so on... everytime we decrease the overall loss.

#### Classification 

- See AdaBoost : somewhat dates algorithm.
- Classufy between -1 and 1 
- Use exponential loss function 
- Output a number between -inft and inft 
- This reperesents how confident they are in the prediction 

- We train a weighted sum of trees 


### XGBoost 
- Brings least squares in adaboost into one place. 
- XGBoost is extremely well written. 
- Understanding XGBoost theoretically is one thing but tuning hyper parameters is another question. 

- If data set is not small but not large enough for neeural nets then XGBoost is the best algorithm out of anything 
- Easy to train 
- For regression and classification the firist thing we do is XGBoost.

- Loss function is binary cross-entropy.s
- Normal decision treee... search through all features, all possible split points, and find the best split that ioptimises the finromation gain (aka rthe loss).
- This is s a lot of work to do if we have a lot of features or a alot of possible split points. 
- Traaining a forest of these trees is even more expensive.

- XGBoost uses binary entoropy which is a coo,mpliacted loss function 
- So we assume second tree correction is small and take the taylor series expansion of it. 
- Then split this between each node and solve these independently. 

-  But how do we know second tree is small?
- We regularis eto make this so.
- We penalise trees with a lot of leaves and trees that make large corerecitons to previous tree. 

### Hyperparameters 
- NB : use XGBoost own library for XBoost, not gradient boosting in sklearn. 

- Hyperparameters help us prevent overfitting 
- For example the max depth. 

- There is anotehr important hyperparameter : Shrinkage 
- RAther than selecting optimal output at each leaf node, we put a constant in 
front of otput of leaf node, so that instead of taking optiaml step we take some fraction 
of ioptimal step. 
- We should think of this as the learning rate.
- It's not clear why this makes such a difference, but it does! 
 
- LEarnign rate : eta 
- REgularisation paraemters : lambda 
- Number of jobs : for paralellisation 
- Max depth : depth of each tree 
- Subsampling parameters : incljude elements of bafggign such as sampling a given number of features / bootstrapping.
- Number of estimators : set this high like 20000. This is how many trees are in the forest. We would think this over fits but what stops t. atis easy stopping. This looks at change of performacne from previous step and stops if it's small. So may as wel set high and then use early stopping.

Tips
- Train loss might decrease at each step, but if validation goes up then we shuold stop. 
- Can write own loss functions in XGBoost. 
- API is similar to that of SKLearn : But need to provide two datasets to XGBoost when we are trainig. One is training data and the other is evalusation or test data. Thi sised used to calcualte performance when we're doing warly stopping. So three sets in all, train, test, validate.

### Other options 
- LightGBM : Same algorithms are XGboost. Developed by MLEs at microsoft. Changes the way that training is done at tree lelve. They gro width wise rather than deoth wise. This is faster.
- Cat Boost : There is no need to one hot encode categorical data because it does it for you. That's the only difference. 
- NGBoost : XGBoost can't handle uncertainties in its predictions. This is very new. 
- PGBML : Again similar but also handles uncertainties.

### Disadvantages o XGBoost 
- Can't work out uncertaintites.

### Extensions 
- Implementing own loss functions.  

### Conclusing remarks 
- Only slightly harder to use than randmo forests but usually performs much better.
- Handles missing data very easily. 
- COmputationally efficient - scales well to other data sets. 
- Can use any twice differentible loss function 

- Bosseting allow us to build powerful ensembles 
- In Baggin we average, in boostngi we correct the last model. 

- Bagging and boossting are often taught together but they're quite different. 
- Only similarity is ensembles 
- Bagging easier to understand, boosting is usualy better. 


