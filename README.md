# Module 17 Supervised Machine Learning
## Challenge: Credit Risk Analysis
### Background
The assignment states that "Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, we’ll need to employ different techniques to train and evaluate models with unbalanced classes." To solve this challenge, we are asked you to use imbalanced-learn, imblearned and scikit-learn libraries to build and evaluate models using resampling.
For this project, we have been asked to use a dataset from from LendingClub.
We will use technologies such as VS Code's rendition of Jupyter notebook, IPython to mine the dataset and run it through the required models.<br/>
### Actions and Results<br/>
#### Actions: resampling
The data we are using show that there are 68470 low-risk loans and 347 high-risk ones. Our next step has been to split our data into Training and Testing sets and initiated 'oversampling it'.

||pre|rec|spe|f1|geo|iba|sup|
|---|-----|-----|-----|-----|-----|-----|-----|
|high_risk|0.01|0.73|0.57|0.02|0.64|0.42|101|
|low_risk|1.00|0.57|0.73|0.72|0.64|0.41|17104|
|avg/total|0.99|0.57|0.73|0.72|0.64|0.41|17205|

The precision for the low-risk loans is high suggesting that there may exist a positive bias towards the low-risks loans. In addition, the balanced accuracy at 0.65 is a low given the inherent bias towards low-risk loans. Another method may yield different results or confirm the bias that we've identified. Let see what results we get when retraining the data with SMOTE oversampling.
||pre|rec|spe|f1|geo|iba|sup|
|---|-----|-----|-----|-----|-----|-----|-----|
|high_risk|0.01|0.63|0.68|0.02|0.66|0.43|101|
|low_risk|1.00|0.68|0.63|0.81|0.66|0.44|17104|
|avg/total|0.99|0.68|0.63|0.81|0.66|0.44|17205|
<br/>
We also tried undersampling and finally combined over and undersampling. The result for this last attempt is below. 
There isn't a drastic changes as the accuracy score for this step is at 0.64.

||pre|rec|spe|f1|geo|iba|sup|
|---|-----|-----|-----|-----|-----|-----|-----|
|high_risk|0.01|0.69|0.40|0.01|0.52|0.28|101|
|low_risk|1.00|0.40|0.69|0.57|0.52|0.27|17104|
|avg / total|0.99|0.40|0.69|0.56|0.52|0.27|17205|

### Summary
Using the Balanced Random Classifier yielded better results as the accuracy score for this model yielded a 87% accuracy percentage. The AdaBoost qualifier however offered an accuracy score of 62%.

 
