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
