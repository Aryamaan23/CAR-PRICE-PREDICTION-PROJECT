# CAR-PRICE-PREDICTION-PROJECT
It is a project in which we have to predict the buying price of cars using machine learning algorithms.
We are given a train dataset and test dataset in the form of csv(Comma Separated Value)files.
Shape of train dataset is (2000,13).
Shape of test dataset is (509,11).
The target varibale in this problem is buying_price.
We have to predict the buying_price for test dataset.
I have concantenated the train and test dataset into one dataframe df.
Libraries used in the code:
1.numpy
2.pandas
3.matplotlib.pyplot
4.seaborn
Then I have used tail and head functions to have a idea about the train and test data.
I have used info function to check the null value count in each feature of the dataframe and the type of values present in each feature.
Usage of describe function is done to have a complete knowledge about the dataset like mean,median,std,etc.
I have used set_indexfunction to set v_id as the index column.
Then I have plotted the heatmap using the seaborn library to analyse which features contain the null values graphically.
After visualising the heatmap I found that buying_price and profit had the maximum null values.
So I decided to drop those columns with the help of a condition.
After dropping these two column the shape of the concatenated dataframe became (2509,10)
I used for loop to check unique values in each column of dataframe.
After that I checked the count of unique values and what unique values are present in each column.
I used seaborn and matplotlib library to check the skewness of the graph and found out it to be -0.01.
After finding the skewness I used seabornlibrary to plot the heat map. With the help of this heatmap I found out the correlation between each feature of the dataset.
I analysed the heatmap and with the help of some conditions I found out the highest correlated features with the buying_price.The features which were highly correlated with the buying_price were:
1.on road old
2.on road now
3.buying_price itself
I also analysed the correlation of these 3 features with the buying_price graphically.
When I analysed them graphically I found out that they are correlated with the buying_price linearly. On analysisng the graphs I found out that data points were not much scattered. So at that point of time I decided that Linear Regression linear model is the right fit to make the prediction.
I prepared my training data for fitting.
from sklearn.model_selection I imported KFold,cross_val_score
from sklearn.metrics I imported make_scorer,r2_score
I imported these in order to check the performance of my LinearRegression linear model.
I fitted my LinearRegression linear model on my data.
After fitting I checked the score of my model.
I got a score of 0.9956852622456099 as output which is quite good.
I got my predcitions as a numpyarray with 509 int values.
Since my prediciton is a numpy array I used pd.DataFrame to convert it into a dataframe so that I concatenate it with v_id of test dataset.
Then I defined a new dataframe as submission_test1 in which I concatenated the v.id of test dataset and my predicitons.
But the demand of the task was to submit the prediction in the form of csv file.
So in order to do that I converted my dataframe submission_test1 into a'sample_submission.csv' with the help of to_csv()function.
To check my csv file I opened and read it in my code itself and finally I got the desired output.







