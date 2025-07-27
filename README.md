# Hybrid-GAN-Architecture

# 🧠 Hybrid ViT-CNN GAN for Text-to-Image Synthesis

**A research project developed during my university internship exploring hybrid generative models by combining Transformers and Convolutional Neural Networks for text-to-image generation.**

## 📌 Overview

This project presents a novel **hybrid text-to-image synthesis model** that integrates a **Transformer-based generator** with an enhanced **CNN-ViT hybrid discriminator**. The goal was to explore how combining the **local feature extraction power of CNNs** with the **global attention mechanism of Vision Transformers (ViTs)** can improve the quality, stability, and efficiency of image generation from text prompts.

We used a subset of the **CIFAR-10 dataset** (specifically the *cat* class) to test the model’s capability in capturing fine-grained semantics from input text and generating coherent, visually aligned images.

## 🛠️ Model Architecture

### Generator (Text → Image)
- **Text Encoder**: BERT-based encoder to extract dense embeddings.
- **Latent Noise Vector**: Combined with text features to initiate generation.
- **Generator Core**: Transformer-based multi-layer encoder-decoder structure.
- **Output**: Image (64x64) with pixel values scaled via `tanh()` activation.

### Discriminator (Image + Text → Real/Fake)
- **Hybrid Image Encoder**: 
  - Initial layers use CNNs for local feature extraction.
  - Followed by a ViT block to encode global image context.
- **Text Conditioning**: Text embeddings are fused with image features.
- **Final Classifier**: Outputs probability of image being real or fake, conditioned on text.

## 🔍 Key Contributions

- ✅ Novel hybrid GAN architecture combining ViT and CNN components.
- ✅ Enhanced discriminator stability and performance with local+global context awareness.
- ✅ Demonstrated faster convergence and better semantic alignment vs traditional GANs.

## 🧪 Experiments

### Dataset
- **CIFAR-10** (cat class only)
- Images resized to 64x64 and normalized.

### Training Details
- **Epochs**: 100
- **Batch Size**: 16
- **Optimizer**: Adam (`lr=0.0001`, `betas=(0.5, 0.999)`)
- **Loss Function**: Binary Cross Entropy (BCE)

### Metrics & Evaluation
- Visual fidelity of generated images.
- Semantic alignment between text prompts and generated images.
- Training convergence (tracked via generator & discriminator loss).


## 🧠 What’s Next?

- 🚀 Scaling to higher resolutions (128x128, 256x256).
- 🐶 Extending to multiple CIFAR-10 classes or more complex datasets like MS-COCO.
- 🤖 Exploring diffusion-based improvements or multi-modal fusion layers.


