# Diffusion-Based Image Inpainting on Masked MNIST

This project demonstrates how diffusion models can be applied to the task of **image inpainting** on the MNIST dataset. Specifically, it focuses on reconstructing masked regions in grayscale digit images using a denoising diffusion probabilistic model (DDPM).

---

## Features

- **Custom Binary Masking Pipeline**  

- **Simple Denoising Diffusion Probabilistic Model (DDPM)**  
  The model is built from scratch using PyTorch, implementing the standard forward (noising) and reverse (denoising) diffusion process. The forward process adds Gaussian noise over T steps, and the reverse process learns to predict the noise at each step.

- **U-Net Inspired Architecture for Noise Prediction**  
  A lightweight convolutional neural network is used to estimate noise in each diffusion step. This network takes the masked image and the current timestep as inputs and predicts the noise to be removed.

- **Time Embedding for Diffusion Steps**  
  The model incorporates timestep embeddings to condition the noise predictor on the current step of the diffusion process. This helps the network learn time-dependent denoising behavior.

- **Loss Function: Noise Prediction Objective**  
  The network is trained using the standard DDPM objective — predicting the added noise using mean squared error (MSE) between predicted and true noise values.

- **Training and Inpainting Visualization**  
  The notebook includes detailed visualizations of:
  - Noising over time (forward process)
  - Denoising step-by-step reconstruction (reverse process)
  - Final inpainted output vs. masked input

- **Evaluation on Unseen Masked Digits**  
  After training, the model is tested on new masked MNIST samples to assess generalization to unseen occlusions.

- **No External Dependencies or Pretrained Models**  
  Everything is implemented from scratch using basic PyTorch and runs entirely in a Jupyter Notebook environment, making it accessible and easy to modify or extend.


---

## 📂 Project Structure

