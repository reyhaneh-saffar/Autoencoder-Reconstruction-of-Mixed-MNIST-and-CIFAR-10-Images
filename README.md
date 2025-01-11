This project explores the use of an autoencoder neural network for data compression and reconstruction. The datasets CIFAR-10 and MNIST were preprocessed, combined, and used to train the model, with promising results in reducing reconstruction loss.


### Data Processing
- **Dataset Preparation**:
  - CIFAR-10 and MNIST datasets were transformed and normalized to ensure compatibility.
  - MNIST images were converted to RGB and resized to match CIFAR-10 dimensions.
  - Both datasets were standardized in terms of image size and pixel value distribution.
- **Mean Image Computation**:
  - Corresponding images from CIFAR-10 and MNIST were averaged to create new "mean images."
  - This process enriched the dataset by combining features from both datasets, producing unique training and testing data.
- **Dataset Structuring**:
  - The mean images were reshaped to fit the input format required for model training and evaluation.
  - Structured training and testing datasets were created to ensure consistency and diversity for the model.

### Training the Autoencoder
- **Model Construction**:
  - The autoencoder was composed of:
    - **Encoder**: Compressed input data into a latent space representation using convolutional layers with non-linear activation functions.
    - **Decoder**: Reconstructed input data from the latent space using transposed convolutional layers, restoring spatial dimensions.
  - A loss function measured reconstruction accuracy, optimized using backpropagation.
- **Training Process**:
  - **Data Handling**: Training and testing datasets were loaded into data loaders for efficient batching and shuffling.
  - **Training Loop**:
    - Over 50 epochs, the autoencoder iteratively learned to compress and reconstruct input data.
    - The optimizer adjusted model parameters based on reconstruction loss.
  - **Evaluation Loop**:
    - After each epoch, the model was tested on unseen data to monitor its generalization ability.
    - Reconstruction loss was recorded for both training and testing datasets.

### Results and Insights
- **Performance Metrics**:
  - Training Loss: Decreased from **0.9747** in the first epoch to **0.2641** in the final epoch.
  - Testing Loss: Reduced from **0.9674** to **0.2609**.
- **Visualization**:
  - A plot of training and testing losses over 50 epochs showed steady decreases, indicating effective learning and generalization.

