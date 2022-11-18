# Neural_Network_Charity_Analysis

## Analysis Overview
____________________
The purpose of this analysis was to utilize neural networks and build a model to help predict which companies should be allocated the charity funds. In doing this we would need to take our historical data and define our targets and what outcomes we would like to achieve. 


## PreProcessing
________________
To start with we removed some of the unneeded fields that did not support the predictive model. So EIN and Name were removed, these could always be refrenced back to the index in a future update if needed.

![This is an image](https://github.com/Bren42/Neural_Network_Charity_Analysis/blob/main/Resources/pre_proccessing_removals.png)

Those items removed other catogories we reviewed to determine if we needed to bucket any data items. Application Type had all values under 500 and classification had items under a thousand combined into one category.

From here we used one hot encoder on all categorical features to encode them to a numeric.

![This is an image](https://github.com/Bren42/Neural_Network_Charity_Analysis/blob/main/Resources/one_hot_enc_preopt.png)

after this was completed it was time to complete our first model. 

![This is an image](https://github.com/Bren42/Neural_Network_Charity_Analysis/blob/main/Resources/pre_opt_model.png)

in the first model we chose to use two times the input layers and had 80 neurons, th esecond layer would posses 30 neurons. We chose to use RELU for both hidden layers and the output layer would be sigmoid. This was run at 100 epochs to fit the model. 

### RESULTS
___________

Our first model returned decent, but not acceptable accuracy rates. 

![This is an image](https://github.com/Bren42/Neural_Network_Charity_Analysis/blob/main/Resources/pre_opt_results.png)

as seen in the results we achieved a 65% percent accuracy. This seemed ok for a first pass, but we would need to start running optimizations to see if we could figure out if the low accuracy was due to noise in the data, not enough neurons, a poor activation method or a combination. 


### Optimization Results
________________________

There were 3 attempts made to reach a higher than 75% accuracy rating.

First Attempt
_____________
 MODEL:
![This is an image](https://github.com/Bren42/Neural_Network_Charity_Analysis/blob/main/Resources/model_1.png)


RESULTS:
![This is an image](https://github.com/Bren42/Neural_Network_Charity_Analysis/blob/main/Resources/results_1.png)

In this model I removed the application type and the classification fields from the dataframe. As the dataset and inputs was now less I also moved the amount of neruons down in the hidden layers from 80/30 to 60/10.

Our outcomes look slightly promising, we went from 65% to 68% accuracy. Not a massive improvement but moving in the right direction. 


Second Attempt
______________
 For the second attempt at optimization I left the data as it was. Instead we would reconfigure the activation modes in the model to see if we got better results, as well as add a third hidden layer. 
 
 MODEL: 
![This is an image](https://github.com/Bren42/Neural_Network_Charity_Analysis/blob/main/Resources/model_2.png)

RESULTS:
![This is an image](https://github.com/Bren42/Neural_Network_Charity_Analysis/blob/main/Resources/results_2.png)

As we can see from the results, this did not have the intended effect, we dropped accuracy by 15 points. This was obviously not the model to use. 


Third Attempt
_____________
In the third attempt the dataset was still left as it was from the first attempt, again we went to the hidden layers and activation types to see if we could get a better outcome. First layer was dropped to 40 neurons, but switched to a linear activation and we increased the size of the second layer of neruons. 

MODEL:
![This is an image](https://github.com/Bren42/Neural_Network_Charity_Analysis/blob/main/Resources/model_3.png)


RESULTS:
![This is an image](https://github.com/Bren42/Neural_Network_Charity_Analysis/blob/main/Resources/results_3.png)

as we can see there were improvements again, so we were moving back in the right direction. The results weren't 75% but they were heading in the correct direction. This model would still need improvement and it seems like if we take optimization model 1 and add some neruons and hidden layers as well as change the activations types we could get to 75%. 






