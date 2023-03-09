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

![image](https://user-images.githubusercontent.com/76435009/224118624-baf8d482-6801-4f56-a60f-b08f1472d9e8.png)
![image](https://user-images.githubusercontent.com/76435009/224118772-ed55d023-8c64-4bb8-b542-08f96a620305.png)
![gif](https://user-images.githubusercontent.com/65583643/165344458-0afe1612-d236-4959-b607-e0b7b25018bb.gif)
