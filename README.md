# Neural_Network_Charity_Analysis
![image](https://user-images.githubusercontent.com/85843030/139080476-355271ea-c45f-4e09-9890-650ff6668b73.png)


## 1. Project Overview
The aim of the project is to use Neural Network to analyse the dataset from Alphabet Soup, for future decision making regarding funding approvals
to various organizations.

## 2. Resources
Jupyter Notebook
Python

## 3. Coding summary
### 3.1 Deliverable 1
<ins>Preprocessing the data obtained from 'charity_data.csv'</ins>

1. Import the dependencies, and read in the dataset as a DataFrame
2. Clean the data set
3. Check the unique values
4. Decide on which columns to use for binning
5. Plot a density plot to determine the limit for the rare occurances & adjust the values to replace in the appropiate Column
6. Generate a categorical variable list
7. Create a OneHotEncoder instance
8. Merge the OneHotEncoder features and drop the originals
9. Split the preprocessed data into features and target arrays
10. Split the data into a training and testing dataset
11. Create a StandarScaler instance

### 3.2 Deliverable 2

<ins> Compile, Train and Evaluate the Model</ins>

12. Define the number of input features and hidden nodes for each layer
13. Add activation function `relu` to the hidden node layers
14. Add activation function `sigmoid` to the output layer
15. Check the structure of the model
16. Add checkpoint that saves the model's weight every 5 epochs
17. Model's loss and accuracy is printed
18. Save the results to an HD5 file

## 4. Analysis
### 4.1 Analysis-Deliverable 1 & 2

After training, scaling, and transforming the dataset, the traing feature data is added to the neural network.
For the two first deliverables, a basic Neural Network Model is built, using the `Keras` `Sequential class`.
43 input features and 2 hidden layers with 80 & 30 nodes are used. The hidden layers are added using `Keras` `Dense Class`.
The structure of the model is shown here:

![image](https://user-images.githubusercontent.com/85843030/139085329-75fb6b41-f86e-4215-9226-95cf08795823.png)

Next, we use some optimization functions, to shape and mold the neural network model while it is being trained. For this we use
`adam optimizer`, `binary_crossentropy` loss function, and we also want to measure the quality of the model, which we can do by using
model predictive accuracy `accuracy`.




