

<!-- PROJECT LOGO -->
<br />

<p align="center">
  <a href="https://github.com/Amg9794/Image-compression-using-GAN">
    <img src="https://github.com/Amg9794/Image-compression-using-GAN/blob/main/gan.png" alt="Logo" width="300" height="200">
  </a>
  <h3 align="center">Generative Image Compression</h3>
  <p align="center">
    Image Compression using GANs
    <br />
    <a href=https://github.com/Amg9794/Image-compression-using-GAN><strong>Explore the repository»</strong></a>
  </p>

</p>

> tags : image compression, gans, generative networks, celeba, deep learning, pytorch 



<!-- ABOUT THE PROJECT -->

## About The Project

In the modern world, a huge amount of data is being sent across the internet every day. Efficient data compression and communication protocols are of great research interest today. We focus on the compression of images and video (sequence of image frames) using deep generative models and show
that they achieve a better performance in compression ratio and perceptual quality. We explore the use of GANs for this task. We know that generative models such as GANs and VAE can reproduce an image from its latent vector. We ask the question whether we can go the other direction — from an image to a latent vector. Research, though limited, has shown that these types of methods are quite effective and efficient. We further employ lossy compression and use Elias coding to reduce the vector size.


The project uses a pretrained Progressive GAN trained on CelebA-HQ dataset from Facebook Research which gets automatically downloaded. 

### Instructions to run

To train (compress the images) the model run,

```sh
python main.py --train-model True
```

This generates a folder in the `results` directory for each run. The generated folder contains the compressed images using different schemes and bit rates.

To evaluate the model on the compressed images run,

```sh
python main.py 
```

This calculates the average PSNR and SSIM values across different runs, and generates `avg_psnr.txt` and `avg_ssim.txt` in the `results` directory.



## Model overview

The architecture of the model is shown below. We freeze the GAN model and optimize for the best latent vector using gradient descent.

![Transformer](https://github.com/Amg9794/Image-compression-using-GAN/blob/main/model.jpg)



<!-- RESULTS -->

## Results

We evaluate the models on the Structural Similarity Index (SSIM) and Peak Signal to Noise Ratio (PSNR) between the original image and reconstructed image.

| Compression method | SSIM | PSNR | CR |
| :------------------------------------------: | :-----------------: | :------------------------------------------: | :------------------------------------------: |
| GAN        | 0.79 | 26.48 | 176 × |
| Lossy compression 8bits | 0.77 | 25.06 | 412.5 × |
| Lossy compression 6bits | 0.67 | 25.06 |  495 ×  |
| Lossy compression 4bits | 0.46 | 25.06 |  559 ×  |
|     JPEG Quality 1%     | 0.51 | 19.96 | 99 × |

Figure below compares the image quality of reconstruction for a sample image for different schemes.

![Transformer](https://github.com/Amg9794/Image-compression-using-GAN/blob/main/results.jpg)








