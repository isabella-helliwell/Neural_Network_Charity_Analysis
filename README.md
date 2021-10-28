# Neural_Network_Charity_Analysis
![image](https://user-images.githubusercontent.com/85843030/139080476-355271ea-c45f-4e09-9890-650ff6668b73.png)


## 1. Project Overview
The aim of the project is to use Neural Network to analyse the dataset from Alphabet Soup, and to create a binary classification model that can predict if Alphabet Soup funded organization will be successful based on future dataset.

## 2. Resources
- Jupyter Notebook, version 6.3.0
- Python, version 3.7.10
- Input dataset:charity_data.csv
- Image taken from https://appen.com/blog/what-are-neural-networks/ 


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
Next, we train, and evaluate the model using the test data.

![image](https://user-images.githubusercontent.com/85843030/139088616-65836c02-84aa-4514-b63d-44acbe2a78bb.png)

### 4.2 Analysis-Deliverable 3
For this deliverable, the aim is to try and achieve a target predictive accuracy higher than 75%. 
Several attempts are made to increase the accuracy and these are summarized below:
1. <ins><b>OPT1: Drop more columns:</ins></b> 'STATUS', 'ORGANIZATION', 'USE_CASE', 'SPECIAL CONSIDERATIONS' & 'AFFILIATION' columns dropped.
Everything else is unchanged.

![image](https://user-images.githubusercontent.com/85843030/139145032-aa8b1ed8-c20d-4fc7-b54e-d354b611ed6d.png)


![image](https://user-images.githubusercontent.com/85843030/139144340-09b7b49d-17c0-42db-b741-4e107883395a.png)


2. <ins><b>OPT2: Add 1 more hidden layer, with 10 nodes:</ins></b> 


![image](https://user-images.githubusercontent.com/85843030/139146044-2320fa42-8f59-477e-a4db-9bd559525ec0.png)


![image](https://user-images.githubusercontent.com/85843030/139293140-44633dff-7a88-4813-bd29-591c5e113a5e.png)


3. <ins><b>OPT3: increase the bin size, decrease no of bins:</ins></b> 


![image](https://user-images.githubusercontent.com/85843030/139270685-c538e384-76a2-4755-b4df-153735354ef3.png)


![image](https://user-images.githubusercontent.com/85843030/139277744-e7948639-3d70-48c3-9155-1dbdbf703ef8.png)


4. <ins><b>OPT4: decrease the bin size, increase no of bins:</ins></b> 


![image](https://user-images.githubusercontent.com/85843030/139279420-941eecbc-6797-41ae-ac17-9f45380112c8.png)

![image](https://user-images.githubusercontent.com/85843030/139279883-c50f1e7d-8e3b-412a-adba-596091b20cbe.png)


## Summary

A summary of all 5 models are shown below. The plots show the accuracy and loss vs iterations.
We can see that when we start running the model,the loss is great (shown in red). As the number of iterations (epochs) increase, the loss decreases
significately at first few iterations, but than stabilizes towards the end of the iterations. This trend is true for all plots.
For the accuracy plots(shown in green), it behaves opposite to the loss plot, meaning, as no of iterations increase, the accuracy level increases 
significantely at first and it stabilizes somewhat as the iterations increase. This trend is valid for all plots.

![overview](https://user-images.githubusercontent.com/85843030/139285327-9569ccec-0e1e-4d95-be92-e185c1f2b051.png)


## Conclusion

To achieve a target predictive accuracy of 75%, several attempts have been made to optimize the  model accuracy by manipulating data and codes. Looking at the 
summary plot, we can see that using optimization 1, did not improve the accuracy at all, infact the outcome was worst comparing to the other plots.
Looking at the remaining plots, the outcome was not significantly changed with respect to the optimizations made. 
Ideally we want the loss as close to 0 as possible and accuracy as close to 1 as possible. 
In this instance, the model is only 73% accurate in predicting potential future successful Alphabet Soup funded organizations.

Since we only have tabular data, and the outcome did not change much after all the optimizations, we could try and use Scikit-Learn's `RandomForestClassifier` class
to see if the model accuracy will change.
