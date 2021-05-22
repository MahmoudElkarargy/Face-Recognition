# Face-Recognition
Face recognition means that for a given image you can tell the subject id. Our database of subject is very simple. It has 40 subjects.

It's a university project for Pattern Recognition at Faculty of Engineering, Alexandria University. Computer and Communication Program.

<br>

## FIND COLAB LINK FOR THE PROJECT.
https://colab.research.google.com/drive/1py-d6fU1s_O-ldskP-n8W-KZ12CCI8Ym?usp=sharing

## Before running!
    1. Download archive.zip, which includes the 40 persons images.
    2. Download non_faces_scaled.zip, which includes non faces images.

<br>


## Below we will show the needed steps to achieve the goal of the assignment.
 ### 1. Download the Dataset and Understand the Format.
    a. The dataset has 10 images per 40 subjects. Every image is a grayscale image of size 92x112.
 ### 2. Generate the Data Matrix and the Label vector.
    a. Convert every image into a vector of 10304 values corresponding to the image size.
    b. Stack the 400 vectors into a single Data Matrix D and generate the label vector y. The labels are integers from 1:40 corresponding to the subject id.
 ### 3. Split the Dataset into Training and Test sets.
    a. From the Data Matrix D400x10304 keep the odd rows for training and the even rows for testing. This will give you 5 instances per person for training and 5       instances per person for testing.
    b. Split the labels vector accordingly.
 ### 4. Classification using PCA.
    a. Use the pseudo code below for computing the projection matrix U.
    Define the alpha = {0.8,0.85,0.9,0.95}
    b. Project the training set, and test sets separately using the same projection matrix.
    c. Use a simple classifier (first Nearest Neighbor to determine the class labels).
    d. Report Accuracy for every value of alpha separately.
    e. find a relation between alpha and classification accuracy?
### Classification Using LDA.
    a. Use the pseudo code below for LDA. We will modify few lines in pseudocode to handle multiclass LDA.
      i. Calculate the mean vector for every class Mu1, Mu2, ..., Mu40.
      ii. Replace B matrix by Sb.
      
               𝑚
          𝑆𝑏 = ∑ 𝑛𝑘(𝜇𝑘 − 𝜇)(𝜇𝑘 − 𝜇)𝑇 𝑘=1
          
        Here, m is the number of classes, 𝜇 is the overall sample mean, and 𝑛𝑘 is the number of samples in the k-th class.
      iii. S matrix remains the same, but it sums S1, S2, S3, ...S40.
      iv. Use 39 dominant eigenvectors instead of just one. You will have a projection matrix U39x10304.
    b. Project the training set, and test sets separately using the same projection matrix U. You will have 39 dimensions in the new space.
    c. Use a simple classifier (first Nearest Neighbor to determine the class labels).
    d. Report Accuracy for the Multiclass LDA on the face recognition dataset.
    e. Compare the results to PCA results.
### Classifier Tuning.
    a. Set the number of neighbors in the K-NN classifier to 1,3,5,7.
    b. Tie breaking at your preferred strategy.
    c. Plot (or tabulate) the performance measure (accuracy) against the K value. This is to be done for PCA and LDA as well.
### Compare vs Non-Face Images.
    a. Download non-face images and make them of the same size 92x112. and try to solve the classification problem faces vs. Non-faces.
      i. Show failure and success cases.
      ii. How many dominant eigenvectors will you use for the LDA solution?
      iii. Plot the accuracy vs the number of non-faces images while fixing the number of face images.
      iv. Criticize the accuracy measure for large numbers of non-faces images in the training data.
### Bonus.
    a. Use different Training and Test splits. Change the number of instances per subject to be 7 and keep 3 instances per subject for testing. compare the results     you have with the ones you got earlier with 50% split.
    
