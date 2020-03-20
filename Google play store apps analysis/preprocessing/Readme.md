# Google play store apps installs prediction
### Data preprocessing
* In order to get clean data, first step we need to do is data preprocessing
* Original data (googleplaystore.csv) includes 13 columns and 10841 data records.
1. Load the data, but delete the records which app name can't be decoded in unicode-8.  
2. Drop the columns which are not related to installs and also not the factors developer can control before release the app (ex: number of review, app names, etc), and thus remains 7 columns left in total.
3. Drop the records with no value. 
4. Installs is the target label we are going to predict, and thus we split data into three class(installs<=10000、 10000<installs<=1000000, installs>1000000) 
5. Remaining columns will be the feature label that machine will learn to predict installs, including category, size, price, content rating, last updated, and version. 
6. Label the feature columns into each different class dpends on unique value within the column. 
7. Min_max scaler on all the columns, and thus the label will all be converged in the range of [0,1]

Implement methods of decreasing dimension:
1. SVD
2. PCA
3. NMF
4. Autoencoder

Classifier:
1. SVM
2. Naiive Bayes
3. Decision tree

Result:
* The prediction accuracy is around 50% , which means that it's pretty hard for machine to distinguish these apps according to these 6 features.
* The best classifier is Decision tree, which prediction accuracy is 57%
* The least dimension we can decrease is 3, the result of four methods shows no nuch difference.
* when the dimension decrease under 2, the result of four methods shows significant difference and the best method is Autoencoder, which still remains 50%.



