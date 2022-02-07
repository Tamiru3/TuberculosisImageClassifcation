# Tuberculosis Chest X-Ray Image Classification: A Deep Learning Approach

### By: Tamiru Berhanu-Denka
 
## Overview

According to the World Health Organization(WHO), Tuberculosis, is the second killer infectious diseses, killed 1.5 million people in 2020 alone next to COVID-19.
Increases in the overall age of the population and the rise of drug-resistant TB have reinforced the need for rapid diagnostic improvements and new modalities to detect TB and drug-resistant TB, as well as to improve TB control. Artificial Intelligence (AI) models are being used as a diagnostic aid in many places. Excellent accuracy of the deep learning approach has been widely accepted and used in medical image classification applications. Many recent works based on deep learning technology have promoted the development of intelligent diagnostic systems, which can help human experts make better decisions about patients’ health. The aim of this project is to use Convolutional Neural Network (CNN) to identify and classify tuberculosis images from healty/normal chest x-ray images.

## Data 

Atotal of 985 985 CXR images from Tuberculosis patients was collected follwing procedural authorization request at the The National Institute of Allergy and Infectious Diseases (NIAID). The pictures are loacted at the NIH/NIAID TB portal (https://tbportals.niaid.nih.gov/)(https://sharingwith.niaid.nih.gov/browse/shares/646). Normal CXR images of 3500, was also downloaded from the RSNA CXR dataset: RSNA pneumonia detection challenge dataset ( https://www.kaggle.com/c/rsna-pneumonia-detection-challenge/data. A total of 4485 Chest X-rays labelled as either tuberculosis(985) or normal(3500) were used for in this study. 

## Methodology

Before starting the Neurl Network, as part of preprocessing step, data was rescaled by dividing by 255 since the images are x-ray (greyscale). I also resized each image to  64 X 64 pixels to maintain the uniformity of each x-ray image. Using the ImageDataGenerator, a 80% - 20% split on the  train set - validation set respectively was set to create a validation set. Sicne I am predicting an image, it is considered as binary class mode (binary classifcation).
Modeling was started by using the simple perceptron neural network as a baseline model, then trained multiple CNN models by hyperuning to achieve the highest accuracy and recall socore. Deatil iterations of the models are clearly indicated in the final notebook. To get the maximum accuracy out of a neural network model, it is always advisable to pick the right optimizer with the right parameters. Various literatures has shown the use of Adam over stochastic gradient descent(SGD)(https://openreview.net/pdf?id=SJx37TEtDH; https://ramseyelbasheer.io/2021/06/20/a-2021-guide-to-improving-cnns-optimizers-adam-vs-sgd/). Another study by Ashia C. Wilson et al., 2018 also suggestes to reconsider the use of Adam in neural networks(https://arxiv.org/pdf/1705.08292.pdf) explaining the generlization issue as " solutions found by adaptive methods generalize worse (often significantly worse) than SGD, even when these solutions have better training performance". For this modeling, I have compared both Adam and SGD. The accuracy and recall socres were higher in all times where the optimzation was using Adam. Therefore, Adam, an optimization algorithm was selected based on the performace for image classifcation. The Adam optimizer makes use of a combination of ideas from other optimizers. It uses an exponentially decaying average of past gradients. Adam also employs an exponentially decaying average of past squared gradients in order to provide an adaptive learning rate.  

## Results

The third CNN  model resulted the highest recall scores of 98.07% and the accuracy score of 98.66% which is slightly lower than the accuracy socre of 99.18% of the first cnn model. These socre changes could be attributed to the changes I made in this model including, increasing the number of epoches, adding addional layers of the pooling and dropout has enhanced the increase in the overall recall score while maintaining the the realtive higher accuracy score. The trade of between accuracy and recall scores were evaluated in each model and the model with the the maximum ability to find all the tuberculosis cases within a dataset was selected. Therefore, the third CNN model is the model of choice.


<img width="257" alt="image" src="https://user-images.githubusercontent.com/37712711/151293001-5b3b7b90-054b-4c64-ba14-b16b30e7334f.png">


## Conclusion 


Compared to all models, the highest recall scores of 98.07% was recored on the third CNN model. This implies that, 98.07% of the time the radiologist or the physician could minimize the false negative error. Maximum reduction of false negative error is mandatory to avoid misdiagnosing the patients with Tuberculosis as being healthy, which would lead the patient to spread the bacteria to the healthy population. This in turn helps to spread of tuberculosis. The accuracy socre of 98.66% also indicates, how radiologists/physicians can accurately classify the tuberculosis x-ray image from the normal one. Overall, the model result shows the diagnositc power of deep learning in correctly classifying TB chest x-ray images. Thus, I recommend the radiologists and pulomonlogists to use this model as a primary decision tool in their rountine Tuberculosis screening especially in multidrug resistant tuberculosis. I also recommend the Center for Infectious Disease Imaging (CIDI) at NIAID/ NIH and the World Health Organization to use this information in their Tuberculosis diagnosis gudeline and resrarch agenda.

## Environment setup detail


## Respository Structure
```
├── CXRImageData                                   <- folder containing saved x-ray images for Main Notebook
├── project_presentation.pdf                       <- PDF version of the final project presentations
├── README.md                                      <- Brief summary of a README file for reviewers 
├── TB_Image_Classification_ Final_Notebook.ipynb  <- Main notebook of the project in Jupyter notebook
├──                
```