In this zip file theere are 3 different jupyter notebook files for threre different method.
In all methods I assumed the 'cost' column as the feature to be predicted as a bid price.

1)criteo_LinearLassoRegr.ipynb: 
In this one I tried Featurehasher to convert the data into a real feature based dataset as it it is stated in the link below.  
https://ailab.criteo.com/criteo-attribution-modeling-bidding-dataset/

Although Campaign and Cat1.. Cat9 fields have numeric data in it but they are not continous data. In fact each of them have to be mapped mapped into a fixed dimensionality space using the Hashing Trick. Please refer to the explanation about below link.

https://ailab.criteo.com/criteo-attribution-modeling-bidding-dataset/

The resulted dataframe turned out to be a large dataset with high dimensionality (2.8 GB size and 16777225 columns)

I tried to reduce the size by converting the dtypes but at the end it was too diffucult to work with and it constantly crashed the memory. The Lasso regression didn't finish for more than 1 hour.

2) criteo_DecisionTree.ipynb:
I tried to use DecisiontreeRegression because first dataframe caused so many memory problems. We know that Decision tree based ML algorithms work fine on both continous and categorical data no need to make any conversion. So In this work I used the datafrmae as it is I only removed uid column.

3) criteoDecTreeCV.ipynb:
In this run i tried to implement decisiontreeregression in a gridsearchCV. The data is time dependent data so I tried split dataset in a forward chaining strategy. 
fold1: training [day1 to 19], test[day 20]
fold2: training [day1 to 19], test[day 21] 
fold3: training [day1 to 19], test[day 22] 
fold4: training [day1 to 19], test[day 23] 
