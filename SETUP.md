# Setup
The model can be run in the file final_project.ipynb (from the notebooks directory). In the file, there are two labeled sections. The first section (labeled "function and class definitions") defines the model and various functions that are used, and the second section (labeled "model funtionality demo") demonstrates the model functionality.

In the "model functionality demo" section, there are four scripts: The first script organizes the data from the csv file into different datasets (train, validation, test). The second script loads in the model weights, runs the model on the entire test set, and prints out the biomass prediction tensor. For visualization purposes, it also displays the first four grass images from the test set alongside their state, species, height, NDVI value, and targets. The third and fourth script are the scripts used for model training and model test evaluation, respectively. 

For reference, each script is commented at the top with what it does.


To try out the model, first run all the code in the "function and class definitions" section to compile all the functions and classes used for the model. Then, in the "model functionality demo" section, run the first script to load in the data first; run the second script to have the model make some predicitions on the test set and see some of the input data. To try out the model training or model test evaluation, run the third and fourth scripts.