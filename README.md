# The Task 

We are going to be developing data processing pipelines for data set consumer_complaints_train.csv . 

you can download the data from here : https://www.dropbox.com/s/45uw7mbh7iv7ppw/Consumer_Complaints_train.csv

# Classes used 
[ add list of data processing classes that you will be making use of ]

* VarSelector 
*  DataFrameImputer(
*  string_clean
*  custom_fico
*  creat_dummies
*  custom_el
* ...

# Groups of Variable 
[Add different groups of variables here which will go through same data processing pipelines]

* List of variables present
** V1': 'Date received',
 'V2': 'Product',
 'V3': 'Sub-product',
 'V4': 'Issue',
 'V5': 'Sub-issue',
 'V6': 'Consumer complaint narrative',
 'V7': 'Company public response',
 'V8': 'Company',
 'V9': 'State',
 'V10': 'ZIP code',
 'V11': 'Tags',
 'V12': 'Consumer consent provided?',
 'V13': 'Submitted via',
 'V14': 'Date sent to company',
 'V15': 'Company response to consumer',
 'V16': 'Timely response?',
 'V17': 'Consumer disputed?',
 'V18': 'Complaint ID'
 
 * # Conisderations:
 * 1. convert to date type: V1, V14
* 2. impute missing, create dummies: V2,V4,V7 v8,V9,v10, V11,v12,v13,v15,v16, v17,  V3, V5 - very low fill rate;
* 3. drop: v18 complaint id is not useful 
* 4. text pre-process: v6, V7

# Notes :

* Base File Stats:
** Total records: 4,78,421
** 18 Columns in base file
* 

* give **good** reasons if you decide to drop any of the variables 
* for text columns you can use tfidfVectorizer from sklearn [write your own class which makes use of it internally .you will find it here : sklearn.feature_extraction.text.TfidfVectorizer ] . A simple object of this class will do the job and you can use it as is in your custom class .

```python
TfidfVectorizer(analyzer='word',stop_words='english',max_df=0.8,min_df=0.01,max_features=200)
```
* Make sure that you add a class to standardise numeric columns. Use sklearn's Standard Scaler [ write your own class which makes use of it internally .you will find it here : sklearn.preprocessing.StandardScaler] 
* Before creating TfIdf features for column `Consumer complaint narrative` , make sure to remove `XXXX` from it . 
* The reason you might want to write your own custom classes for TfidfVectorizer : It doesnt return pandas dataframe by default . It returns a sparse matrix instead which you can convert to dense numpy array using `.toarray()` . It does have `get_feature_names` function which you can make use of.
* Similarly standard scaler also returns an array instead of a pandas dataframe. Additionally it doesnt have any `get_feature_names` functions . 
* Please include a text file named `.gitignore' in your local repo and use it to exclude big data files from being uploaded to the repo [google for how to use it ]
* Have two python [.py] files added . one for the custom classes and another for where you make use of these classes to build a pipeline . If in the process you end up using any additional files , please make sure that you add them to .gitignore 

Fork this repo and get working . Once done please raise a pull request which i will review and suggest changes if any needed . 

