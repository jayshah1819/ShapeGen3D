# Text-to-Image Generation Using CLIP and U-Net

## Author: Jay Shah  
## Date: 04-26-2024  

This project implements a text-to-image generation model using a pre-trained CLIP model for text encoding and a simple U-Net architecture for image generation. The model learns to generate images based on textual descriptions by leveraging diffusion-based denoising techniques.

---

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Preprocessing](#preprocessing)
- [Model Architecture](#model-architecture)
- [Training](#training)
- [Generating Images](#generating-images)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Contact](#contact)

---

## Introduction
This project utilizes:
- **CLIP Model**: To encode text into feature vectors.
- **U-Net Architecture**: To generate images by first up-sampling and then down-sampling the input.
- **Diffusion Model**: To progressively refine the generated image over multiple iterations.

---

## Dataset
The dataset consists of images labeled with different text descriptions of geometric shapes in different arrangements. The images are stored in `DATA_DIR`, and each label represents a different spatial configuration of shapes.

To access the dataset, email me at [jayshah.jk.jk18@gmail.com](mailto:jayshah.jk.jk18@gmail.com).

---

## Preprocessing
The dataset is preprocessed by:
1. Loading images and filtering non-image files.
2. Applying transformations such as resizing, flipping, and normalizing pixel values.
3. Converting images to tensors for PyTorch processing.

---

## Model Architecture
The model consists of:
- **Text Encoder**: A linear layer projecting CLIP-generated text features.
- **U-Net Architecture**: A simplified U-Net with residual connections to preserve image details.
- **Time Embedding**: To incorporate timestep information into the model.

---

## Training
- **Optimizer**: Adam optimizer with a learning rate of `0.001`.
- **Loss Function**: L1 loss between predicted and actual noise in diffusion.
- **Training Duration**: 100 epochs with periodic loss logging.

---

## Generating Images
To generate images from text:
```python
text = "square on top of circle"
generate_text_to_image_samples(text)
```
This runs the model to iteratively refine an image based on the input text prompt.

---

## Installation
### Prerequisites:
- Python 3.x
- PyTorch
- NumPy
- Matplotlib
- Pillow (PIL)
- torchvision
- OpenAI CLIP

### Installation Steps:
```bash
pip install torch torchvision numpy matplotlib pillow clip-by-openai
```

---

## Usage
1. Clone the repository:
```bash
git clone <repo_link>
cd <repo_folder>
```
2. Update `DATA_DIR` with the path to your dataset.
3. Run the training script:
```bash
python train.py
```
4. Generate images:
```bash
python generate.py
```

---

## Results
The model progressively generates better images over 100 epochs. Sample results can be visualized using:
```python
sample_plot_image()
```

---

## Contact
For dataset access or inquiries, email me at:  
📧 [jayshah.jk.jk18@gmail.com](mailto:jayshah.jk.jk18@gmail.com)

