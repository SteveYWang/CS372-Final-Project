# Grass Biomass Prediction Model
This project is based on a Kaggle contest (https://www.kaggle.com/competitions/csiro-biomass/overview) to create a model that predicts biomass data for Australian grass based on images and various measurement values. This biomass data is important for farmers to know whether a piece of land has enough food for their animal herds. Current biomass estimation models are either unrealiable or very tedious to implement, so a machine learning estimation tool can greatly help farmers for their biomass estimation tasks.

# What It Does
An input to the model consists of an image of grass, the state in Australia the grass is from, the grass species, the average grass height, and the grass NDVI value (a type of biological value). The model outputs in grams the predicted measurements for five biomass values: dry green vegetation, dry dead material, dry clover biomass, green dry matter, and total dry biomass. Based on the Kaggle instructions, the model reads the image filepath and measurement values from a csv file. The model outputs an nx5 tensor (where n is the number of inputs) containing predictions about the 5 biomass values for each input. The model works by first passing the grass image to a fine-tuned ResNet, where the final layer has been replaced by an identity layer. Then, the output of this ResNet is concatnated with the data for the other inputs (with one-hot encodings for categorical data). This concatnated information is then passed to a neural network that outputs the 5 biomass values.

# Quick Start
In the file final_project.ipynb (from the notebooks directory), there are two labeled sections. The first section defines the model and various functions that are used, and the second section demonstrates the model functionality.


The model functionality section contains four code cells. The first cell organizes the data from the csv file into different datasets (train, validation, test). After running the first cell, the second cell loads in the model weights, runs the model on the entire test set, and prints out the biomass prediction values. For visualization purposes, it also displays the first four grass images from the test set alongside their state, species, height, NDVI value, and targets. 

The third and fourth cells in the model functionality section are used for model training and model test evaluation, respectively. 

For reference, each code cell is commented at the top with what it does.

# Video Links
Project Demo: https://www.youtube.com/watch?v=SKkmmxSpPtw

Technical Walkthrough: https://youtu.be/wxeFlaSWUY0

# Evaluation
Model performance was measured using MSE of the predicted versus actual biomass values.

### Validation performance was measured on different training drop-out percentages:

10% drop-out best validation: 215.41

30% drop-out best validation: 149.43

50% drop-out best validation: 160.23

Based on these values, a drop-out rate of 30% is chosen.

### Validation performance was measured on SGD vs Adam optimizer for a 30% drop out rate:
Adam best validation: 149.43
SGD best validation: 969.3

Based on these values, Adam optimizer is chosen.

### Final test evaluation
Using the paramters trained from a 30% drop out percentage and an Adam optimizer, a final test MSE of 142.57 is acheived.


# Individual Contribution
This was a one-person project, so all parts of it were done by myself.
