# machine_learning_SuperResolution
## Supervised Image super-resolution and denoising

### Data
Source: ~~https://drive.google.com/file/d/1cf1SMuXGuAwhW-iEKOhtDUBwo475TjL2/view~~ (Requires Illinois Credentials)
Updated Google Drive link: https://drive.google.com/open?id=1u2Q_LJnJxq_SQ_pO59jmOtJwYfhgLmPs

The dataset is a collection of 20,000 X-ray images at each at both high (128x128) and low (64x64) resolution broken. There are 16,0000 training images (at both 128x128 and 64x64) as well as 3,999 test images (only at 64x64). The task is to leverage these 16,000 samples to generate a high resolution version of each of the 3,999 low-res samples.

### Basic Methods
A very deep convolution neural net is used for this project.

It includes 18 convoluted layers (with RELU activations and 64 layers of feature extractions) and at the end the outputs are merged with the input images. For preprocessing, the 64x64 image is expanded to 128x128 using LANCZOS interpolation, after that a image is divided into 16 32x32 sub-images.

The 32x32 image is then the input to the model (with the corresponding 32x32 high dosage image as the truth).

### Paramters
The learning rate was set to 0.001 after experiments. 

All but the last 2000 images are used for training purposes, and the last 2000 are used for testing purposes.

### Reference
This model was inspired by the VDSR model proposed here https://arxiv.org/pdf/1511.04587.pdf.
