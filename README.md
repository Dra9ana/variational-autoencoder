# Variational Autoencoder Project 

## Project Overview
This project explores **Variational Autoencoders (VAE)**, a generative model first introduced in the paper "Auto-Encoding Variational Bayes." The VAE model is applied to three datasets: MNIST, FashionMNIST, and SVHN. In contrast to the original work, which uses a simple perceptron architecture, this project employs a **Convolutional Neural Network (CNN)** for both the encoder and decoder. The Adam optimizer is used, and training is conducted with various hidden layer sizes for better results on image data.

### Key modifications compared to original paper and achievements:
- **CNN architecture** for encoder and decoder
- **Adam optimizer** with a batch size of 128
- Experimentation with different **latent space dimensions** (N = 2 for grayscale images)
- **Results comparison** with the original paper, showing improved performance using CNNs
- Analysis of **latent space visualization** and **random image generation**

## Datasets Used
1. **MNIST**: A dataset of 60,000 training and 10,000 test grayscale images (28x28 pixels) representing handwritten digits (0-9).
2. **FashionMNIST**: Similar in structure to MNIST, but with images of various clothing items.
3. **SVHN (Street View House Numbers)**: A more challenging dataset consisting of 73,257 color images of house numbers, with 26,032 test images. Each image contains digits (0-9) with additional background noise.

## Model Architecture
- **Encoder**: Convolutional layers followed by a fully connected layer, encoding input images into a latent space representation.
- **Decoder**: A mirrored architecture of the encoder, reconstructing images from the latent space.
- **Latent Space**: Latent dimensions of 2 were used for grayscale images to allow better visualization, while larger latent dimensions were explored for colored images.

## Results
- **MNIST Dataset**: 
    - For latent dimensions of 16, 100, and 200, the generated images showed increasing levels of detail, with significant improvement when increasing from 16 to 100. The difference between 100 and 200 was marginal.
    - Average total loss: 132.39  
    - Reconstruction loss: 123.63  
    - KL loss: 8.76  
    - Visualized latent space clusters were well-separated for different digit classes.
    
- **FashionMNIST Dataset**: 
    - Similar trends to MNIST, with higher latent dimensions yielding more detailed images.
    - Average total loss: 254.21  
    - Reconstruction loss: 247.38  
    - KL loss: 6.83  

- **SVHN Dataset**: 
    - Due to the increased complexity of colored images, a hidden layer size of 1024 and a latent dimension of 200 were used.
    - Average total loss: 1908.62  
    - Reconstruction loss: 1888.50  
    - KL loss: 20.12  

## Conclusion
The results from this project highlight the effectiveness of using **Convolutional Neural Networks** for VAEs, especially when working with image data. The model performed well on simpler datasets (MNIST, FashionMNIST), while the more complex SVHN dataset required a significantly larger model to achieve reasonable performance. Despite the increased complexity, the results are promising and show the potential of VAEs for image generation tasks.

## References
- "Auto-Encoding Variational Bayes" by Kingma & Welling
