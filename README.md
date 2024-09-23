# Neural-Style-Transfer
Neural Style Transfer (NST) is a deep learning technique that applies the artistic style of one image (style image) to the content of another image (content image). This is achieved by using deep neural networks to separate and recombine the content and style of different images.

# Neural Style Transfer: Traditional vs Fast Method

## Overview

This repository demonstrates two different approaches for **Neural Style Transfer**:
1. **Traditional Neural Style Transfer** (iterative, custom implementation)
2. **Fast Style Transfer** using pre-trained models from **TensorFlow Hub**

  

   ![Alt text describing the image]( https://github.com/Adhi-Git-hub/Neural-Style-Transfer/blob/main/TensorFlow%20Hub%20Model-1.jpg)


Neural Style Transfer (NST) is a technique that allows us to apply the artistic style of one image to the content of another image. The traditional approach uses a deep neural network with multiple iterations to adjust the content image, whereas the fast style transfer method uses a pre-trained model for real-time performance.

## 1. Traditional Neural Style Transfer

### Methodology
- **Model**: Uses the **VGG19** network for extracting style and content features.
- **Training**: The content image is updated iteratively over multiple epochs (10 epochs in the current example) to minimize the style and content loss.
- **Loss**: Combines content loss and style loss (calculated using the **Gram matrix** of style features).
- **Time Taken**: Around **20 minutes** for 10 epochs on a typical CPU machine.
- **Use Case**: Best for high-quality artistic stylization, but not suitable for real-time applications.

### Key Steps
1. Load the content and style images.
2. Preprocess images to feed them into the VGG19 model.
3. Define the loss function (content loss + style loss).
4. Use gradient descent to iteratively update the content image to match the style.

### Performance
- **Time-consuming**: Requires multiple iterations (epochs) to generate the final output.
- **Hardware Dependent**: Significantly faster on GPUs, but still slower compared to fast style transfer models.

## 2. Fast Style Transfer Using TensorFlow Hub

### Methodology
- **Model**: Pre-trained fast style transfer model from **TensorFlow Hub**.
- **Training**: No training required. The model is already trained on various styles and can apply styles in a **single forward pass**.
- **Time Taken**: **Less than 5 seconds** to stylize an image.
- **Use Case**: Suitable for real-time applications like mobile apps (e.g., PicsArt), where fast and efficient stylization is required.

### Key Steps
1. Load the pre-trained model from TensorFlow Hub.
2. Pass the content and style images into the model.
3. Get the stylized output in a single forward pass.

### Performance
- **Real-time**: Inference takes just a few seconds.
- **Pre-trained**: The model is already optimized for applying styles instantly.
- **Mobile-Friendly**: Suitable for real-time applications on mobile devices and other platforms requiring instant feedback.

## Comparison of Both Methods

| **Aspect**                     | **Traditional Neural Style Transfer**               | **Fast Style Transfer (TF Hub)**                   |
|---------------------------------|----------------------------------------------------|---------------------------------------------------|
| **Training Required**           | Yes (for each new image)                           | No (pre-trained)                                  |
| **Time for Stylization**        | 20 minutes for 10 epochs                           | Less than 5 seconds                               |
| **Model Size**                  | Large (VGG19, multiple layers)                     | Lightweight (optimized for speed)                 |
| **Inference Speed**             | Slow (needs iterative training)                    | Fast (single forward pass)                        |
| **Hardware Dependency**         | Needs powerful GPU for faster performance          | Optimized for real-time, even on mobile devices   |
| **Use Case**                    | High-quality artistic stylization                  | Real-time stylization for mobile apps and others  |

## How to Run

1. **Traditional NST**: Run the `traditional_nst.py` file. The content image will be stylized over multiple epochs (default: 10 epochs).
2. **Fast NST**: Run the `fast_nst.py` file. The content image will be stylized in a few seconds using the TensorFlow Hub model.

## Future Improvements

- **Hybrid Models**: Combining the flexibility of traditional methods with the speed of fast models.
- **Mobile Optimization**: Further optimization using frameworks like **TensorFlow Lite** to make it even more efficient for mobile platforms.

## References

- book - generative-deep-learning-teaching-machines-to-paint-write-compose-and-play

