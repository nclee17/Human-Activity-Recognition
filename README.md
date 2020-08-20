# CNN_LSTM Model for Human Activity Recognition

Human Activity Recognition (HAR) from smartphone sensors signal dataset from [UCI Machine Learning Repositry](https://archive.ics.uci.edu/ml/machine-learning-databases/00240/UCI%20HAR%20Dataset.names)
The goal is to classify the type of movement amongst six activities:
- Walking
- Walking Upstairs
- Walking Downstairs
- Sitting
- Standing
- Laying

## Dataset

The link below shows a video of the 6 activities recorded in the experiment with one of the participants:

<p align="center">
  <a href="http://www.youtube.com/watch?feature=player_embedded&v=XOEN9W05_4A
" target="_blank"><img src="http://img.youtube.com/vi/XOEN9W05_4A/0.jpg"
alt="Video of the experiment" width="400" height="300" border="10" /></a>
  <a href="https://youtu.be/XOEN9W05_4A"><center>[Watch video]</center></a>
</p>

## Dataset Description

> The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used.

The almost raw data will be used: only the gravity effect has been filtered out of the accelerometer as a preprocessing step for another 3D feature.

## Dataset Overview

The dataset is a recording of 30 people's smartphone signal while performing the different aforementioned activities.
Each of the 3 signals (Body Acceleration, Angular Velocity, Total Acceleration) are recorded as 3-axial (xyz) data points.

There are 10,299 observations within the dataset, with training and test set split at 70% / 30%.

IMG

## Data Visualisation

Simple lineplot for each activity was produced:
e.g.

IMG

This is an misrepresentation of the xyz axial data being separated as different lines, therefore 3D plot is produced instead.
e.g.

IMG

The above 3D plot is difficult to interpret and human eyes cannot distinguish when the observation starts and ends. A treatment of the 3-axial data to calculate the distance of the data point at each timesteps from the origin (x,y,z=0,0,0)
e.g.

IMG

The above graphs can clearly present the notable difference in pattern between the different activities.

## Model

The CNN-LSTM model was trained with data directly feeding into the neural network without feature engineering.

GridSearchCV was used for hyperparameter tuning, and EarlyStopping was used on the final model.
