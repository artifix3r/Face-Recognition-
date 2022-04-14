# Face-Recognition-
Predict who is in the picture  
Data set : https://scikit-learn.org/stable/modules/generated/sklearn.datasets.fetch_lfw_people.html#sklearn.datasets.fetch_lfw_people

# Problem Description ad load data 
face recognition is the supervised classification taks of identifying a person who is an image her or his face. In this project we used lfw people data set
For loading our data i used fetch_lfw_people function from sklearn . 
Face recognition is the supervised classification task of identifying a person from an image.
Our data set consist 6 peoples images. Our images are small. A feature vector that encodes the intensity of e
very pixel will have high dimensions. Training from such high dimensional data colud require many samples to avoid over-fitting . 
Instead , we will use PCA to compactly represent the images in terms of a small number of principal components .

 # Loading data_ </br>
  _data=fetch_lfw_people(min_faces_per_person=70, resize=0.4)_ </br>
  
# Split data randomly to train and test sets and use PCA
   _X,y=data.data,data.target_ </br>
   _X_train,X_test,y_train,y_test=train_test_split(X,y,random_state=11)_</br>
reduce all of the instances to 150 dimensions and train a logistic regression classifier. The data set contains classes, 
Scikit learn automatically creates binary classifier using the one versus all strategy behind the scens 
_pca=PCA(n_components=150,whiten=True)_<br>
_X_train_PCA=pca.fit_transform(X_train)_<br>
_X_test_PCA=pca.transform(X_test)_<br>
_print(X_train.shape)_<br>
_ print(X_train_reduced.shape)_<br>
# Results and evaluation 
Finally we evaluate the performance of the classifier using cross-validation and a test set.  The avereage per-vlass F1-score of the classifier trained on the full data was 0.77 ,
but required significantly more time to train and could be prohibitively slow in an application with more training instances. 
</br>

# Results 

![image](https://user-images.githubusercontent.com/99141535/163468908-690c5906-da2e-4005-bdff-39ddcb665cf9.png)
