# Machine Learning Final
## Team members:
 - ## <span style="color:green">521H0489: Hồ Hữu An</span>.
 - ## <span style="color:green">521H0491: Trần Nhựt Anh</span>.
 - ## <span style="color:green">521H0290: Đỗ Minh Quân</span>.

Bank Term Deposit Predictions

This `dataset`, titled Direct Marketing Campaigns for Bank Term Deposits, is a collection of data related to the direct marketing campaigns conducted by a Portuguese banking institution. These campaigns primarily involved phone calls with customers, and the objective was to determine whether or not a customer would subscribe to a term deposit offered by the bank.

The dataset contains various features that provide insights into customer attributes and campaign outcomes. These features include:

- `Age` : The age of the customer.(numeric)
- `Job` : The occupation of the customer.(categorical: "admin.","unknown","unemployed","management","housemaid","entrepreneur","student", "blue-collar","self-employed","retired","technician","services")
- `Marital Status` : The marital status of the customer.(categorical: "married","divorced","single"; note: "divorced" means divorced or widowed)
- `Education` : The education level of the customer.(categorical: "unknown","secondary","primary","tertiary")
- `Default` : Whether or not the customer has credit in default.(binary: "yes","no")
- `Balance` : The balance of the customer's account.(numeric)
- `Housing Loan` : Whether or not the customer has a housing loan.(binary: "yes","no")
- `loan` : Whether or not the customer has a personal loan. (binary: "yes","no") 

### related with the last contact of the current campaign
- `Contact Communication Type` : The method used to contact the customer. (categorical: "unknown","telephone","cellular")
- `Day` : The day of the month when the last contact with the customers was made. (numeric)
- `Month` : The month when the last contact with the customers was made.
- `Duration` : The duration (in seconds) of the last contact with customers during a campaign. (numeric)

### other attributes:
- `Campaign Contacts Count` : Number of contacts performed during this campaign for each customer (numeric, includes last contact)
- `pdays` : number days passed since previously contacted form previous camapign (numeric, -1 means client was not previously contacted)
- `previous`: number of contacts performed before this campaign and for this client (numeric)
- `poutcome` : outcome from previous marketing campaign (categorical: "unknown","other","failure","success")

### Output variable (desired target):
- `y` : has the client subscribed a term deposit? (binary: "yes","no")

The purpose behind this dataset is to train a predictive model that can determine if a given customer will subscribe to a term deposit based on these various features. By analyzing historical data on successful and unsuccessful subscription outcomes, patterns can be identified which help predict future subscription behavior.
## Sample Data
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>age</th>
      <th>job</th>
      <th>marital</th>
      <th>education</th>
      <th>default</th>
      <th>balance</th>
      <th>housing</th>
      <th>loan</th>
      <th>contact</th>
      <th>day</th>
      <th>month</th>
      <th>duration</th>
      <th>campaign</th>
      <th>pdays</th>
      <th>previous</th>
      <th>poutcome</th>
      <th>y</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>21675</th>
      <td>55</td>
      <td>retired</td>
      <td>married</td>
      <td>secondary</td>
      <td>no</td>
      <td>168</td>
      <td>no</td>
      <td>no</td>
      <td>cellular</td>
      <td>19</td>
      <td>aug</td>
      <td>79</td>
      <td>2</td>
      <td>-1</td>
      <td>0</td>
      <td>unknown</td>
      <td>no</td>
    </tr>
    <tr>
      <th>37612</th>
      <td>32</td>
      <td>admin.</td>
      <td>single</td>
      <td>secondary</td>
      <td>no</td>
      <td>-133</td>
      <td>yes</td>
      <td>no</td>
      <td>cellular</td>
      <td>14</td>
      <td>may</td>
      <td>119</td>
      <td>1</td>
      <td>352</td>
      <td>2</td>
      <td>failure</td>
      <td>no</td>
    </tr>
    <tr>
      <th>23376</th>
      <td>38</td>
      <td>housemaid</td>
      <td>married</td>
      <td>primary</td>
      <td>no</td>
      <td>3918</td>
      <td>no</td>
      <td>no</td>
      <td>cellular</td>
      <td>27</td>
      <td>aug</td>
      <td>101</td>
      <td>3</td>
      <td>-1</td>
      <td>0</td>
      <td>unknown</td>
      <td>no</td>
    </tr>
    <tr>
      <th>5172</th>
      <td>37</td>
      <td>blue-collar</td>
      <td>married</td>
      <td>primary</td>
      <td>no</td>
      <td>1455</td>
      <td>yes</td>
      <td>no</td>
      <td>unknown</td>
      <td>21</td>
      <td>may</td>
      <td>165</td>
      <td>2</td>
      <td>-1</td>
      <td>0</td>
      <td>unknown</td>
      <td>no</td>
    </tr>
    <tr>
      <th>21524</th>
      <td>33</td>
      <td>technician</td>
      <td>married</td>
      <td>secondary</td>
      <td>no</td>
      <td>81</td>
      <td>no</td>
      <td>no</td>
      <td>cellular</td>
      <td>19</td>
      <td>aug</td>
      <td>671</td>
      <td>2</td>
      <td>-1</td>
      <td>0</td>
      <td>unknown</td>
      <td>no</td>
    </tr>
    <tr>
      <th>44771</th>
      <td>47</td>
      <td>technician</td>
      <td>married</td>
      <td>secondary</td>
      <td>no</td>
      <td>1740</td>
      <td>yes</td>
      <td>no</td>
      <td>cellular</td>
      <td>13</td>
      <td>sep</td>
      <td>502</td>
      <td>1</td>
      <td>490</td>
      <td>1</td>
      <td>failure</td>
      <td>no</td>
    </tr>
    <tr>
      <th>7120</th>
      <td>40</td>
      <td>blue-collar</td>
      <td>married</td>
      <td>secondary</td>
      <td>no</td>
      <td>327</td>
      <td>yes</td>
      <td>no</td>
      <td>unknown</td>
      <td>29</td>
      <td>may</td>
      <td>134</td>
      <td>1</td>
      <td>-1</td>
      <td>0</td>
      <td>unknown</td>
      <td>no</td>
    </tr>
    <tr>
      <th>23505</th>
      <td>34</td>
      <td>management</td>
      <td>married</td>
      <td>tertiary</td>
      <td>no</td>
      <td>3486</td>
      <td>no</td>
      <td>no</td>
      <td>cellular</td>
      <td>28</td>
      <td>aug</td>
      <td>23</td>
      <td>10</td>
      <td>-1</td>
      <td>0</td>
      <td>unknown</td>
      <td>no</td>
    </tr>
    <tr>
      <th>32321</th>
      <td>74</td>
      <td>retired</td>
      <td>married</td>
      <td>secondary</td>
      <td>no</td>
      <td>3771</td>
      <td>no</td>
      <td>no</td>
      <td>telephone</td>
      <td>16</td>
      <td>apr</td>
      <td>159</td>
      <td>1</td>
      <td>-1</td>
      <td>0</td>
      <td>unknown</td>
      <td>no</td>
    </tr>
    <tr>
      <th>43123</th>
      <td>48</td>
      <td>housemaid</td>
      <td>married</td>
      <td>tertiary</td>
      <td>no</td>
      <td>5473</td>
      <td>no</td>
      <td>no</td>
      <td>cellular</td>
      <td>24</td>
      <td>feb</td>
      <td>127</td>
      <td>2</td>
      <td>184</td>
      <td>2</td>
      <td>success</td>
      <td>yes</td>
    </tr>
  </tbody>
</table>
</div>


### Data Preprocessing
- Data Encoding: Label Encoding
- Data Normalization: Min-max scaler
### Basic Models
- Logistic Regression
- KNN
- Decision Tree
- Naive Bayes
- SVM
### Ensemble Learning
- Bagging
- Voting
- Stacking
- Random Forest
- Gradient Boosting
- Adaboost
- XGBoost
- LightGBM
#### Feed Foward Neural Network
#### Reccurent Neural Network
### Overfiting
- Detect Overfitting: StratifiedKFold
- Prevent Overfitting: StratifiedKFold and Early Stopping
### Improve Models
- finding hyperparameter by using grid view for some models
- Handle imbalanced data
- Using StandardScaler instead of MinMaxScaler for Boundary-based models, Neural Networks models
