# Anomaly Detection in Videos
Anomalies in videos are broadly defined as events or activities that are unusual and signify irregular behavior. The goal of anomaly detection is to identify cases that are unusual within the data.

Anomaly Detection System is defined as a real-time surveillance program designed to automatically detect and account for the signs of offensive or disruptive activities immediately.

# Multiple Instance Learning
In MIL, precise temporal locations of anomalous events in videos are unknown. Video-level labels indicating the presence of an anomaly.

Single video is a bag if the instance of video contains the anomaly we label it as a positive bag(anomalus video) else we consider it negative video(normal video).

# Approach
## C3D Architecture
The C3D model is given an input video segment of 16 frames (after downsampling to a fixed size which depends on dataset used) and the outputs a 4096-element vector. The fully connected layers have a size of 4096 dimensions which will be used in the DNN model for calculating the anomaly score.

![image](https://user-images.githubusercontent.com/76435009/224113059-c97fc859-26ff-4e0a-9b30-aae471825b66.png)
![image](https://user-images.githubusercontent.com/76435009/224113382-0f20338f-3966-445a-9caa-23a5a7819f32.png)

## I3D Architecture
The inflated convolution i.e. 3d convolution are performed on the 2D cnn model and after performing number of convolutions on the previous layer and also applying max pooling the results are concated and that result is called an inception module. The I3D Architecture gives a size of 1024 dimensions which will be used in the DNN model for calculating the anomaly score.

![image](https://user-images.githubusercontent.com/76435009/224113773-bdeae3f9-c549-43ff-bea3-4acbb39ac1b0.png)
![image](https://user-images.githubusercontent.com/76435009/224113819-1ad880e2-dea1-4a02-9df9-9e08e1ef5dec.png)

## DNN Model
Feature of 16 frames clip are represented in the form of (4096D and 1024D) were fed into a 3-layer feed forward neural network. This approach will use forward propagation and backward propagation using hinge loss formulation, sparsity and smoothness.

![Screenshot (82)_LI](https://user-images.githubusercontent.com/76435009/224118338-44ef1716-8086-43f4-9765-f2b481837c1e.jpg)

# Results
## True Positive and False Negative Using C3D

![gif](https://user-images.githubusercontent.com/65583643/165344458-0afe1612-d236-4959-b607-e0b7b25018bb.gif)
![gif](https://user-images.githubusercontent.com/65583643/165344552-ef6d0943-c97e-4473-a9ac-36ade9ef0b73.gif)

We have trained our model for 4000 iterations, batch size is 32, learning rate is 0.01 and we have got the sum of hinge-loss, sparsity loss and smoothness loss which is 1.7413.

![image](https://user-images.githubusercontent.com/76435009/224119823-39da42d6-f809-4d45-a182-0bc32bba8158.png)

## True Positive and False Negative Using I3D

![gif](https://user-images.githubusercontent.com/65583643/165344458-0afe1612-d236-4959-b607-e0b7b25018bb.gif)
![gif](https://user-images.githubusercontent.com/65583643/165345590-d53a0fe6-1174-44fb-875a-0cad3b0b4b54.gif)

We have trained our I3d model for 10000 iterations, batch size is 32, learning rate is 0.01 and we have got the sum of hinge-loss, sparsity loss and smoothness loss which is 2.23.

![image](https://user-images.githubusercontent.com/76435009/224120801-61833ed7-381a-43a0-b1a3-566fdb0f4722.png)

# Conclusion
The I3D Trained model gives results with more accuracy then the results generated using the C3D model.
