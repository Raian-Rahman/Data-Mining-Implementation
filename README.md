# Data-Mining-Implementation
## Overview

In this assignment, we were asked to implement two frequent pattern mining algorithms: Apriori and FP-Growth algorithm. Both the algorithms can be used for frequent pattern mining. The key problem of apriori algorithm is has a quite higher time complexity. To solve this time complexity issue FP-growth algorithm was proposed which is a tree based pattern mining algorithm. In this assignment both of the algorithms were implemented in python. The experiment was done on two market basket analysis dataset. These are:

* Groceries market basket dataset.
* Market Basket Analysis

Both dataset contains transaction id as well as some list of items with that order. The header of each of the csv file is shown in table 1. 

<img src="/images/Table 1.PNG" alt="Table 1" style="zoom:150%;" />

As we can see, both the dataset are not preprocessed for using in apriori or fp-growth algorithm. So, we needed to preprocess the dataset so that we can pass the dataset to the algorithm to our model. Preprocessing part, implementation part and comparison part is explained in the later sections. Our, experiment shows that, in the case of apriori the model's speed depends on the number of transaction as well as the support count. While, in case of fp-growth the speed does not vary based on the support count. 



## Preprocessing

To be able to pass the dataset to apriori or fp-growth algorithm, we needed to preprocess the dataset. The dataset was preprocessed in the following fashion. On each row of the table, there will be an order id along with a list of items with corresponding features. Then, we needed to fine-tune the dataset to a specific order to be able to implement the algorithm. An example of both preprocessed dataset is given in figure 1.



<img src="/images/fig1.PNG" alt="fig1" style="zoom:150%;" />



As the dataset was large enough and it took almost 1 hour to run apriori on a complete dataset of 57,000 examples, only the first 1,000 samples were used to ran the apriori algorithm. To compare between both algorithm, the number of samples used on each algorithm should be equal. So, for fp-growth, first $1,000$ examples were used for the experiment.



## Implementation

Both the algorithms were implemented in python. The code implementation notebook for both the algorithm is given in this [repository](https://github.com/Raian-Rahman/Data-Mining-Implementation). While implementing FP-growth, different available codes were tested and finally a code by Asaduzzaman Hirok was used for the experiment. The implementation of apriori algorithm was done by myself.

## Experiments

For this assignment, two different dataset were used for the experiment. First, to check if the algorithms work or not, an example from book was used for testing. Our experiment showed that both the algorithm could generate correct answer for the algorithm. Then both the datasets were passed to both algorithm. The algorithms could find out the solution. But, the speed of both algorithm was not equal. After experimenting, the hyper parameter values are given on table 2. 

<img src="/images/image-20210803125531141.png" alt="image-20210803125531141" style="zoom:150%;" />



## Performance Analysis

After experimenting, it could be seen that the number of support count has a big impact on the running time of the algorithm.  The running time comparison between both algorithm is given on figure 2.

<img src="/images/image-20210803125615119.png" alt="image-20210803125615119" style="zoom:150%;" />



As we can see, in case of lower support count, apriori requires a very high value to  compute  the  association  rule.   But,  as  the  support  count  raises,  the  required time gets lower as the item sets gets pruned even before going into deep level.  But in  case  of  FP-growth  algorithm,  the  required  time  is  almost  similar  for  different number of support count.  But, for different number of samples, the time taken for both algorithm varies.

## Conclusion

As from the comparison part, we can see that the required time for both algorithm has a huge gap.  So from here we can conclude that, if the support count has a lower number,  then  we  can  choose  FP-Growth.   But  if  the  support  count  has  a  higher value, then we can choose apriori algorithm
