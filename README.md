# FaceForesics-Deepfakes-Detection

In this project, a DeepFakes model is trained to detect the forged facial images/videos using a research paper. The algorithm presented in the research paper is implemented and its results are observed. The approach is based on Xception Net which shows promising results when it comes to differentiating between real and fake images. 

### Research Paper: FaceForensics++: Learning to Detect Manipulated Facial Images
### Authors: Andreas R\"ossler and Davide Cozzolino and Luisa Verdoliva and Christian Riess and Justus Thies and Matthias Niessner
### Link: https://github.com/ondyari/FaceForensics

# Training Dataset
Dataset for this project is taken from [Kaggle](https://www.kaggle.com/c/deepfake-detection-challenge/data). The origirnal dataset is of 500GBs. Only few videos from that dataset is downloaded and a pipeline has been created for training of model. More videos can be downloaded and training can be improved further. 

# Preparing data for training
In order to train the model, the video data has to be converted to the image data so that it can be passed to the model for training. Therefore, first of all, the frames from videos are extracted. As this extraction is a long process, I had to use Python's Pickle for this as Google Colab session termiates after some time and all the data is lost. Therefore, I saved the frames in the form of array and then created their pickle files to store those arrays directly on Google Drive. The steps are given below:
1. Extract frames from video
2. Apply face detection to crop the frame
3. Store the cropped images in arrays
4. Store arrays as Pickle files in Drive.

Kindly note that these pickle files now contain the facial image data. One array corresponds to a single video. 

The advantage of using this technique is we have to do video-image conversion only once and then we have the image data. Now whenever we need to train the model, we can directly access the image data stored as pickle files. This saves time in the longer run. Secondly, the data is not lost if Colab's session accidently terminates. 
Colab Notebook for extracting images from videos: 
