# deep-learning-challenge

## Background

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

EIN and NAME—Identification columns
APPLICATION_TYPE—Alphabet Soup application type
AFFILIATION—Affiliated sector of industry
CLASSIFICATION—Government organization classification
USE_CASE—Use case for funding
ORGANIZATION—Organization type
STATUS—Active status
INCOME_AMT—Income classification
SPECIAL_CONSIDERATIONS—Special considerations for application
ASK_AMT—Funding amount requested
IS_SUCCESSFUL—Was the money used effectively

## Results

1.Data processing began with removing irrelevant information by dropping the EIN and NAME identification columns.  The IS_SUCCESSFUL column was identified and assigned the target variable for the initial model and the remaining columns were to be considered features for the model.
2.In the second and third tests (AlphabetSoupCharity_Optimization.ipynb and AlphabetSoupCharity_Optimization2.ipynb), NAME identification column was added back for binning purposes. The data was then split for training and testing sets. 
3.For all 3 tests, the target variable for the model was labeled “IS_SUCCESSFUL” and had the value of 1 for yes and 0 for no. APPLICATION_TYPE and CLASSIFICATION value was used for binning. Several data points were used as a cutoff to bin “rare” variables together with the new value of “Other” for each unique value. Categorical variables were encoded by get_dummies() after checking to see if the binning was successful.

## Compiling, Training, and Evaluating the Model

There were three layers total for the initial model (AlphabetSoupCharity.ipynb) after applying neural networks. The initial model contained 80 and 30 neorons in the hidden layers respectively, and 100 epochs.

<img width="551" alt="model1" src="https://github.com/debralisa/deep-learning-challenge/assets/123344011/7f23e1b6-2f5c-4886-8a5f-0f0f2b1058b7">

The number of input parameters were 43 for the first model and 5,981 parameters were created by a three-layer training model. The first attempt was just over 72.8 % accuracy which was under the desired 75%.

<img width="558" alt="model1train" src="https://github.com/debralisa/deep-learning-challenge/assets/123344011/66a335b0-d174-417c-8e93-b5408bda7ae5">

History_accuracy
<img width="366" alt="hist_acc_model1" src="https://github.com/debralisa/deep-learning-challenge/assets/123344011/e30a6f1b-9ea1-4957-8ad3-a0ddb2a030e3">

History_loss
<img width="312" alt="hist_loss_model1" src="https://github.com/debralisa/deep-learning-challenge/assets/123344011/68f8590d-9355-4504-8d6a-a045f95b5b20">


## Optimization

The second attempt with the “NAME” column in the dataset changed the input parameters to 273 and achieved an accuracy of 77.6% which was much improved from the inital training model of 72.8%. 2,367 parameters were created by a four-layer training model with 7, 14 and 21, respectively and 100 epochs.

<img width="570" alt="model_opt1" src="https://github.com/debralisa/deep-learning-challenge/assets/123344011/5e39e4cb-7b68-4754-b2b4-990f7cac90f9">

<img width="562" alt="model_optimize1train" src="https://github.com/debralisa/deep-learning-challenge/assets/123344011/f6d224ba-8291-46f5-890c-d2689f0a15fa">

History_accuracy
<img width="325" alt="hist_acc_opt1" src="https://github.com/debralisa/deep-learning-challenge/assets/123344011/d3a13fe9-cf05-4249-909b-8c4818ae9fb9">

History_loss
<img width="341" alt="hist_loss_opt1" src="https://github.com/debralisa/deep-learning-challenge/assets/123344011/626abb34-c384-4a97-bfcb-de87b520d7df">

I did train a 3rd model.  I was really determined to improve not just on the predicted accuracy but also with the predicted loss. 453 input parameters were in this final model. 7,039 parameters were created by a four-layer training model with 15, 9 and 9 neurons in the hidden layers respectively and 50 epochs.  I continued with the "NAME" column in the dataset and binning but this time used keras-tuner to achieve an accuracy of 79% and improved the predicted loss from 56% in the initial model, to 46.5% in the first Optimization model and finally to 43.7%.

<img width="636" alt="modeltrainopt2" src="https://github.com/debralisa/deep-learning-challenge/assets/123344011/52ec855f-b4da-4429-903d-8f1239d7eb82">

History_accuracy


History_loss

## Summary

As evidenced from the above visualizatios, the adjustments for modifications did indeed optimize the model to higher than 75% accuracy.  Adjusting the number of epochs did not appear to make a large change in the results.  However, the hidden layers, neurons per hidden layer, adding the "NAME" column and bins, as well as changing the activation functions made large differences in the optimized models. 

I believe making other modifications to the kerastuner would be a good model to continue on an optimized solution.   There are many parameters still to consider when performig the model.  The improvements from my adjustments are a testiment to the viability of this model.
