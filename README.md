# machine_learning_SuperResolution
## Supervised Image super-resolution and denoising

### Training Data
The training data consists of pairs of (simulated) low-dose and high dose chest x-ray images.

### Basic Methods
A very deep convolution neural net is used for this project.

It includes 18 convoluted layers (with RELU activations and 64 layers of feature extractions) and at the end we merge the output with the input image. For preprocessing, we expanded the 64x64 image to 128x128 using LANCZOS interpolation, after that we divided the image into 16 32x32 sub-images.

The 32x32 image was then the input to the model (with the corresponding 32x32 high dosage image as the truth). 
The learning rate we used 0.001 after experimenting with higher rates, we concluded that 0.001 was the best choice. 
We used all but the last 2000 images for training purposes, and used the last 2000 for testing purposes.
This model was inspired by the VDSR model proposed here https://arxiv.org/pdf/1511.04587.pdf. 
