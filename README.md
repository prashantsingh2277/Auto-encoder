# Auto-encoder
Data Preprocessing:

The code reads three datasets: movies, users, and ratings, from MovieLens data.
It also reads the training and test sets (u1.base and u1.test) for collaborative filtering.
Data Conversion:

The data is converted into a user-item interaction matrix, where rows represent users, columns represent items (movies), and the values represent user ratings for movies.
Model Architecture - Stacked Autoencoder (SAE):

The code defines a SAE class that inherits from the PyTorch nn.Module.
The SAE consists of an input layer, two hidden layers (with sizes 20 and 10), and an output layer (same as input size).
The activation function used between layers is the Sigmoid activation function.
Model Training:

The SAE is trained using Mean Squared Error (MSE) loss and the RMSprop optimizer.
The training process aims to reconstruct the input data (user-item interactions) from its encoded representations (hidden layers) using backpropagation.
Model Testing:

After training, the SAE is used to predict user-item ratings on the test set.
The test loss is calculated as the root mean square error (RMSE) between predicted and actual ratings for the test data.
The code follows the steps of training the SAE on the training set and then evaluating its performance on the test set. The final output includes the training loss for each epoch and the test loss, representing the model's accuracy in predicting user-item interactions.

It's important to note that there is a minor typo in the code: "MSELoss" should be replaced with "nn.MSELoss" when defining the criterion for Mean Squared Error loss.
