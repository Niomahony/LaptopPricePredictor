We chose the laptop prices data set from the following link: https://www.kaggle.com/datasets/owm4096/laptop-prices?resource=download

The data set contains 23 columns, examples are CPU frequency, CPU brand name, laptop brand, screen size, ram, storage details, GPU details, laptop weight and more. We chose to use a MLP regression model to predict the price of a laptop based on the attributes of the *laptops*. All visualisations and graphs can be found at the end of this file.

The data set is heavily skewed to the right, meaning there are far more low/mid range laptops than high end. To combat this, we apply the log function to the laptop prices and normalise them.
![image](https://github.com/user-attachments/assets/e314281e-539b-40eb-a617-62b898efefc8)

# Network structure and other hyperparameters

The model we use is the MLP regressor model from SciKit: https://scikit-learn.org/dev/modules/generated/sklearn.neural_network.MLPRegressor.html

There are 4 hidden layers with 100,25,25, and 25 neurons respectively. We found this configuration to output the highest scores while tuning the hyperparameters and found it reduced overfitting.

The activation we use is relu as we are performing regression.

**Hyperparameters:**

The model can iterate a maximum of 1000 epochs.

We set random_state to 1 so we can reproduce the same results by initialising the model with the same random seed.

The inital learning rate is set to 0.0005, which is low, but as we are repeating a max of 10,000 times, this allows the model to learn gradually.

Alpha is set as 0.1 to prevent overfitting and 0.1 was the most efficient value after tuning parameters.

![image](https://github.com/user-attachments/assets/9d86ff00-facb-4065-956c-d968557d2394)
![image](https://github.com/user-attachments/assets/e1b34969-4b8a-471b-82f2-d922b67c67ff)

Here is our beautiful training graph

![image](https://github.com/user-attachments/assets/231c75ee-d186-492a-af3d-14c748a3a8cb)

And finally, the visualisation of predictions using a regression scatter plot
![image](https://github.com/user-attachments/assets/10220e38-4fa4-49b4-96a0-0f55855966b3)

