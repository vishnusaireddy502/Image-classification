# Image-classification

## Challenges
  - *Viewpoint variation:-*  A single instance of an object can be oriented in many ways with respect to the camera.
  - *Scale variation:-* Size of images belonging to the same class may be of different
  - *Deformation:-* Shape of the objects may be varying
  - *Occlusion:-* Some times only small portion of the object is visible
  - *Illumination conditions_- * The effects of illumination are drastic on the pixel level.
  - *Background clutter:-* Objects may blent in background environment
  - *Intra-class variation:-* The classes of interest can often be relatively broad, such as chair. There are many different types of these objects, each with their own appearance.

  ![image](https://github.com/user-attachments/assets/c0d6548f-0528-45f2-9655-24b2edb7b54c)
## Nearest Neighbor Classifier
 Distance between two images is calulates by using the below formula
d1(I1,I2)\=∑p|Ip1−Ip2|  
![image](https://github.com/user-attachments/assets/e3a1b81b-47ab-40de-b720-dcdb7ce886e2)

In nearest neighbor algorithm we will take a image in which we want to predict the label and we will compare it with all the images of trainig set and calculate the distance. The label of the image in traing set with
lowest distane will be the predicted label of the given image

similarly in k-nearest neighbor algorithm we will find k closest images to to the given one and then label is given bases on votes in k closest images

## L1 vs L2 distance
  -L1 may not punish if prediction has high error, as it is a linear function
  -L2 punishes heavly if the prediction has high error
  -But L2 may take outlier in to account also and punish it heavly, as a result the model may learn outlier also, which is not acceptable

  ![image](https://github.com/user-attachments/assets/f7d4df0d-7d02-495e-9ca8-a5c9ee85441f)

## Hyperparametres
<p>
The choice of Model parametres example choice of cost function (L1 or L2),  choice of k in knn algorithm, choice of optimizer etc.. are called *hyperparametres*.\
For choosing hyper parametres we need to test by training on training dataset and verifying on test data set. But we must not use test data too many times it may lead to overfitting.\
Over fitting is condition where model can perform very well on test data and very poor on new data it has never seen before. Thats where we got validation dataset.\
 </p>

## Validation set
<p>
Insted of testing the model on test set after tweaking hyperparametres we check on validation set and choose the best hyperparameters and finally we once check on test data set.
</p>

## Cross Validation

<p>
  Insted of choosing certain datapoints as validation set, we first divide the training set into folds( say 5) and choose 1 fold to be validation set and train and check the accuracies in one iteration. In the next iteration we choose onother fold to 
  be validation set and train the model check the accuracy on validation set. we continue the iterations over all the folds(here 5 times since we have 5 folds).  In knn algorithm we gwt 5 accuracies for eack value of k.
</p>

<p>
  
> ![image](https://github.com/user-attachments/assets/c79217ca-86eb-4a37-b6aa-f0d3c1b6e9f9)
> 
> Example of a 5-fold cross-validation run for the parameter k. For each value of k we train on 4 folds and evaluate on the 5th. Hence, for each k we receive 5 accuracies on the validation fold (accuracy is the y-axis, each result is a point). The trend line is drawn through the average of the results for each k and the error bars indicate the standard deviation. Note that in this particular case, the cross-validation suggests that a value of about k = 7 works best on this particular dataset (corresponding to the peak in the plot). If we used more than 5 folds, we might expect to see a smoother (i.e. less noisy) curve.
</p>

##

  

