# deep-learning-challenge

##Background
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

##Results
Data processing began with removing irrelevant information by dropping the EIN and NAME identification columns.  The IS_SUCCESSFUL column was identified and assigned the target variable for the initial model and the remaining columns were to be considered features for the model.

In the second and third tests (AlphabetSoupCharity_Optimization.ipynb and AlphabetSoupCharity_Optimization2.ipynb), NAME identification column was added back for binning purposes. The data was then split for training and testing sets. 

For all 3 tests, the target variable for the model was labeled “IS_SUCCESSFUL” and has the value of 1 for yes and 0 for no. APPLICATION_TYPE and CLASSIFICATION value was used for binning. Several data points were used as a cutoff to bin “rare” variables together with the new value of “Other” for each unique value. Categorical variables were encoded by get_dummies() after checking to see if the binning was successful.

##Compiling, Training, and Evaluating the Model
There were three layers total for the initial model (AlphabetSoupCharity.ipynb) after applying Neural Networks. The number of hidden nodes were 80 and 30 respectively.

<img width="593" alt="model1" src="https://github.com/debralisa/deep-learning-challenge/assets/123344011/1c9e5089-faad-447f-b031-d8cb0e3587ea">

5,981parameters were created by a three-layer training model. The first attempt was just over 72.8 % accuracy which was under a desired 75% but not too far off.
<img width="682" alt="model1train" src="https://github.com/debralisa/deep-learning-challenge/assets/123344011/2337a4d2-4365-451c-9bd8-3b456882e77c">

##Optimization:
The second attempt with the “NAME” column in the dataset, achieved an accuracy of almost 79%. 

The third attempt with the "NAME" column and using keras-tuner achieved an accuracy of 79%.
