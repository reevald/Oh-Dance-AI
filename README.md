# Let's Learn Traditional Dance! (Final Project: Orbit Future Academy)
Oh Dance offers a real and unique traditional dance learning experience with the support of Artificial Intelligence (Machine Learning). It is said to be real because we will learn to directly demonstrate the basic dance movements and AI will predict and classify the movements we imitate. In addition, the search recommendation feature makes it easier for us to find traditional dances based on keywords, regional names, clothing, accessories, and musical instruments.

## Detection and Classification of Basic Dance Movements (CV)
![How it Works](/image/how-it-works.PNG)
### Datasets
![Sample Dataset](/image/sample-data-cv.PNG)

The dataset used in the training model was obtained from the studio (sanggar) where one of our team members practiced. Each traditional dance has a dataset of 60 images which are evenly divided into three classes of basic dance moves.
### Models

Models for prediction (PoseNet with Fine Tuning) and classification (MobileNet with Fine Tuning) of basic dance movements were built using the help of [Teachable Machine - Pose](https://teachablemachine.withgoogle.com/train/pose) (Google's AutoML Platform). For the implementation using the [Teachable Machine Library - Pose](https://github.com/googlecreativelab/teachablemachine-community/tree/master/libraries/pose). Note: The model that has been created is not included in this repo because it is in the development stage.
### Result and Note
#### Accuracy for Classification Models (Pakarena Dance Movement)
![Accuracy CV Pakarena](/image/acc-pakarena.png)  
#### Loss for Classification Model (Pakarena Dance Movement)
![Loss CV Pakarena](/image/loss-pakarena.png) 
#### Note:
Graphics accuracy looks very good even almost 100% accuracy. However, this happens because of the large number of biases caused by the minimal variation in the dataset used (imbalanced dataset). This also applies to the loss model graph showing a very low predictive error value because the training and testing data have almost identical variations. In addition, currently the dataset used is still being developed (currently 60 images per traditional dance).

### Deploy (Using Teachable Machine Library, Tensorflow Js and P5 Js with Float Model)
[https://oh-dance.appspot.com/learn-dances](https://oh-dance.appspot.com/learn-dances)  
![Deploy CV](/image/deploy-cv.png)

## Search and Recommendation Systems (NLP)
### Installaton
Use pip to install prerequisites on requirements.txt, if you on google colab you can skip this process.
```bash
pip install -r requirements.txt
```
### Usage
Follow the cell on the [notebook research file](https://github.com/reevald/Oh-Dance-AI/blob/main/oh-dance-nlp-v0.ipynb) 
### Datasets
The dataset consists of 5 traditional dance classes with 100 lines of sentences per class. Each line contains keywords, regional names, fashion, accessories, musical instruments and others. 
Dataset collection method using Google Search Engine. Source: [Dataset NLP by Oh Dance](https://github.com/reevald/Oh-Dance-AI/blob/main/DatasetV0.1.csv)
### Models
The model was built using the Long Short-Term Memory (LSTM) algorithm and improved by adding a dropout layer to reduce overfitting in the model.  
![Dropout Layer](/image/dropout.png)
### Result
![Accuracy NLP](/image/acc-nlp.png)  
![Loss NLP](/image/loss-nlp.png)  
![Confusion Matrix](/image/cm-nlp.png)  
The accuracy of the training dataset is 81% while the testing dataset is 84%.
### Deploy (Using Tensorflow Js with Quant Model)
Click search menu:
[https://oh-dance.appspot.com/](https://oh-dance.appspot.com/)  
![Search NLP](/image/v1-nlp.jpg)  
![Search NLP](/image/v2-nlp.jpg)  