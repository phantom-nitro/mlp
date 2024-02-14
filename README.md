# mlp

## svm_classification.py
### model:
  - SVC(kernel='linear', C=1)
### Dataset: 
  - iris data
### Visualization/statistical measure of data: 
  - sns.Facetgrid
### Evaluation: 
  - metrics.classification_report (has precision,recall,f1-score)
  - metrics.confusion_matrix

## diabetes_prediction.py
### model:
  - svm.SVC(kernel="linear")
### Visualization/statistical measure of data: 
  - dataset.describe() (produces count,mean,std,min,25%,50%,75%,max values for all columns)
  - dataset["Outcome"].value_counts() - for each value in Outcome column it counts the number of occurrence
  - dataset.groupby("Outcome").mean() - calculates mean of all column relative to Outcome column values
### data preprocessing:
  - StandardScaler() - makes the data scale-free
### Evaluation: 
  - accuracy_score()

## house_price_prediction.py
### model:
  - XGBRegressor()
### Dataset: 
  - sklearn.datasets.fetch_california_housing()
### data preprocessing:
  - house_price_dataset.isnull().sum() - counts the number of missing values in all columns
### Visualization/statistical measure of data:
  - house_price_dataset.describe()
  - house_price_dataset.corr() - correlation between all columns. if 2 columns increase they are highly correlated.
  - sns.heatmap(correlation, cbar=True , square=True,fmt = '.1f', annot = True, annot_kws={'size' : 8}, cmap='Blues') - visualize the correlation between all columns
### Evaluation: 
  - metrics.r2_score(Y_train, train_prediction) - root squared error
  - metrics.mean_absolute_error(Y_train, train_prediction) - mean absolute error

## fake_news_prediction.py
### model:
  - LogisticRegression()
### data preprocessing:
  - news_dataset.isnull().sum() - counts the number of missing values in all columns
  - news_dataset = news_dataset.fillna(' ') - replace null values with empth string
  - PorterStemmer() - reduce a word to it's root word
  - stopwords.words('english') - remove stopwords words that have no value like 'the' 'a'
  - vectorizer = TfidfVectorizer() - converting text to numerical data (term frequency-inverse document frequency) quantify the importance or relevance of string representations (words, phrases, lemmas, etc) in a document amongst a collection of documents
### Evaluation: 
  - accuracy_score(X_train_prediction, Y_train)

## loan_status_prediction.py
### model:
  - svm.SVC(kernel="linear")
### Visualization/statistical measure of data:
  - loan_dataset["Dependents"].value_counts()
  - sns.countplot(x="Education", hue = "Loan_Status", data = loan_dataset)
### data preprocessing:
  - loan_dataset.isnull().sum() - counts the number of missing values in all columns
  - loan_dataset.dropna() - removes null value rows
  - loan_dataset.replace({"Married":{"No":0,"Yes":1}, "Gender":{"Male":1,"Female":0},"Self_Employed":{"No":0,"Yes":1}, "Property_Area":{"Rural":0,"Semiurban":1,"Urban":2}, "Education":{"Graduate":1, "Not Graduate":0}},inplace=True) - convert categorical columns to numerical values
### Evaluation: 
  - accuracy_score(X_train_prediction, Y_train)

## car_price_prediction.py
### model:
  - LinearRegression()
  - Lasso()
### Visualization/statistical measure of data:
  - car_dataset.info()
  - car_dataset.describe()
  - car_dataset.isnull().sum()
  - car_dataset["Fuel_Type"].value_counts())
### data preprocessing:
  - car_dataset.replace({"Fuel_Type":{"Petrol":0,"Diesel":1,"CNG":2}},inplace=True) - replace categorical data to numerical data
### Evaluation: 
  - linear_test_score=metrics.r2_score(Y_test,linear_test_pred)
  - lasso_test_score=metrics.r2_score(Y_test,lasso_test_pred)
