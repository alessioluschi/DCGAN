# DCGAN
A custom DCGAN model to generate synthetic images with a resolution of 256x256 pixels. Performance is evaluated with gold standard metrics every 20 iterations: Fréchet Inception Distance (FID), Kernel Inception Distance (KID), precision, and recall against the full dataset. Additional metrics are also computed at the end of training: Structural Similarity (SSIM), Haar Perceptural Similarity Index (HaarPSI), Peak Signal-to-Noise Ratio (PSNR), Multi-Scale Structural Similarity (MS SSIM), Multi-Scale Gradient Magnitude Similarity Deviation (MS GMSD), and Mean Deviation Similarity Index (MDSI).

## Description
The designed architecture of the Discriminator exploits spectral normalization, learning rate schedulers, and label smoothing to enhance performance and stabilize the training process. It also implements the following guidelines as introduced by Radford et al. [[1]](#1)
- Replacing any pooling layers with stride convolutions (Discriminator) and fractional-stride convolutions (Generator).
- Using batch normalization in both the Generator and the Discriminator.
- Removing fully connected hidden layers for deeper architectures.
- Using Rectified Linear Unit (ReLU) activation function in the Generator for all layers except for the output, for which _Tanh_ is used.
- Using _LeakyReLU_ activation function in the Discriminator for all layers, except for the output, which uses _Sigmoid_.

### References
<a id="1" href="https://arxiv.org/abs/1511.06434" target="_blank">[1]</a> 
Radford, A., Metz, L., Chintala, S. (2015)
Unsupervised representation learning with deep convolutional generative adversarial networks. 

## Implementation
1. Install <a id="2" href="https://www.anaconda.com/download" target="_blank">Anaconda</a> for your operating system.
2. Create a Conda environment and install the required dependencies using the following commands:
```
conda create -n sngan python=3.9.18 -y
conda activate sngan
pip install -r requirements.txt
```
3. Train the model on your custom dataset of images by setting the parameters in the [definition Jupyter notebook](/definitions.ipynb) and then running the [main Jupyter notebook](/main.ipynb)
