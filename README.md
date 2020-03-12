# Predictive Maintenance using LTSM

This project work is an exploration into the possibility of using sensor data from machine to predict the lifetime of a coponent.
The component data in this case belong to run to failure data of turbo fan from NASA [1].There were two main objectives from the project

1. Predict the remaining useful lifetime of the component
2. To identify if the component will break within a window time span

## Data

The input data consist of sensor data from 21 different sensors along with meta data information on sensor settings, ID ,cycle etc 
as provided in [1]


## Model

The model used in this study is a  Long Short Term Memory Network (LSTM) based on Artificial Recurrent Neural Network philospohy.
The implementation for this model has been inspired from [2].However, the implementation is original considering that the original
model was implemented using Keras whereas PyTorch has been used as the framework for this implementation.PyTorch has been implemnted 
for its advantage with dynamic graphs, library availability and its compatibiliy with Python.

The basic model of consists of following layers  layers

1. LSTM1 
2. Dropout
3. LSTM2
4. Dropout
5. Linear
6. Sigmoid (absent for regression)

## Training

The training has been done by splitting the total data in to train, validation and verfying the generalisation on test data
Ther models above was trained using different value of hidden units size, learning rates,dropout of the LTSM layers.The metric used for training were loss,precision,
accuracy,recall and specificity

## Visualisation

The visualisation for the different metrics has been carried out in tensorboard

## References

1. [Data Source] (https://c3.nasa.gov/dashlink/resources/139/)
2. [Model Reference] (https://github.com/Azure-Samples/MachineLearningSamples-PredictiveMaintenance)
