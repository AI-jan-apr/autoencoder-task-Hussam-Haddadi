MNIST Autoencoder Project
Overview:

This project implements an autoencoder using the MNIST dataset of handwritten digits. The model is trained to learn a compressed representation (latent space) of images and reconstruct them. The learned features are then used for visualization and image similarity search.

Dataset:

The project uses the MNIST dataset loaded via fetch_openml.

70,000 grayscale images
Each image is 28×28 pixels
Flattened into 784 features
Pixel values normalized to range [0, 1]
Preprocessing
Converted data types to float32 for images and int64 for labels
Normalized pixel values by dividing by 255
Reshaped images when needed for visualization
Split dataset into training and testing sets (80/20 split) using stratified sampling

Model Architecture:
Encoder
Input layer: 784 neurons
Hidden layers: Dense (128 → 64)
Output (latent space): 32 dimensions
Decoder
Hidden layers: Dense (64 → 128)
Output layer: 784 neurons with sigmoid activation

Training
Loss function: Binary Crossentropy
Optimizer: Adam
Epochs: 10
Batch size: 256
Validation performed on test set

The model is trained to reconstruct the input images.

Results:
Reconstruction
The autoencoder successfully reconstructs input images
Visual comparison is done between original and reconstructed images
Training Performance
Training and validation loss are plotted
Shows how the model improves over epochs
Dimensionality Reduction
Encoded representations are extracted using the encoder
PCA is applied to reduce latent vectors to 2D
This allows visualization of learned features

Visualization:
2D scatter plot of encoded data
Points are colored based on digit labels
Similar digits form clusters in latent space

Image Retrieval:
A query image is selected from the test set
Its latent representation is computed
Cosine similarity is used to compare it with other encoded images
Top similar images are retrieved and displayed
Technologies Used