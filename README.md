# Malaria_Classification_usingDL
 In this project, I implemented algorithms (VGG16, VGG19, and CNN) to develop a malaria detection system using blood cell images. The goal was to automate the traditional method of identifying malaria, which involves examining blood smears under a microscope.

**Dataset description**: -
We will go through an open dataset made available by the NIH in the United States of 
America. The collection contains micrographs of red blood cells taken from Giemsa-stained 
thin blood smear slides. There are 27,557 images in all, 13,778 of which are infected and 
13,779 of which are not. Dataset images are not all the same size. There are three colour 
channels with a resolution range of 46 × 46 pixels to 385 × 395 pixels (RGB). So we will be 
using this dataset and will be doing the necessary exploratory analysis and pre-processing to 
make the dataset ready for the training the model.
https://www.kaggle.com/datasets/iarunava/cell-images-for-detecting-malaria

![image](https://github.com/nikhil-188/Malaria_Classification_usingDL/assets/84719583/6d741255-fc7c-4bc7-b9b3-5e6da5f0421d)

**How I have implemented**: -
  1. Firstly, we had loaded the dataset into the google collab using its API command and 
  my Kaggle Json file.
  2. Secondly, I had saved the training and testing data in the two variables from the 
  respective paths.
  3. Then we did the data augmentation creating train and validation generators at some 
  calculated shear range, zoom range, vertical flip, horizontal flip, width shift range, 
  height shift range etc to concentrate on the relevant parts of the image.
  4. Then we defined the CNN model with the below hyper parameters and compiled it 
  with Adam optimizer and binary cross entropy. We also used early stopping which 
  helps to stop the model training once the accuracy/ model performance stops 
  increasing or improving.
  5. Then we calculated the validation accuracy and plotted the (accuracy vs epochs) and 
  (loss vs accuracy) graphs to how the model had improved its accuracy with the 
  number of epochs.
  6. Then we used the pre-trained vgg16 model with the pre trained Image Net weights 
  and removed the top layer of the model, so that we can include our own input.
  7. Then we made the compile not to update the weights as they are already trained and 
  disturbing this might affect our model.
  8. Similarly, we compiled the model with Adam and binary cross entropy and plotted the 
  required graph to understand the behaviour of the model training.
  9. We also followed the similar process for the Vgg19 as it is also a variant of Vgg.
  10. Finally, we tabulated the accuracies of the three and wrote a snippet of code to predict 
  the class of an image when the user inputs to our model

**Accuracy and loss graphs for CNN**

![image](https://github.com/nikhil-188/Malaria_Classification_usingDL/assets/84719583/283f0ed9-b4cc-426a-81e3-2e85c8a586d6)

**Accuracy and loss graphs for VGG16**

![image](https://github.com/nikhil-188/Malaria_Classification_usingDL/assets/84719583/62453660-d225-4d83-b63c-5a3b74e213f6)

**Accuracy and loss graphs for VGG19**

![image](https://github.com/nikhil-188/Malaria_Classification_usingDL/assets/84719583/ee4591df-ba11-4031-b9be-204ef59a7aa9)

**Accuracy of the three models**

![image](https://github.com/nikhil-188/Malaria_Classification_usingDL/assets/84719583/6885396e-a1dc-4a84-b1e1-04c10bc69439)

