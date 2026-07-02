# MNIST Handwritten Digit Classification

A machine learning project for training and evaluating models on the [MNIST dataset](http://yann.lecun.com/exdb/mnist/) — 70,000 grayscale images of handwritten digits (0–9), each 28×28 pixels.

## Overview

MNIST is a classic benchmark for image classification. This project loads the dataset, trains a model to recognize digits, and reports accuracy on held-out test images.

## Dataset

| Split      | Images | Labels |
|------------|--------|--------|
| Training   | 60,000 | 0–9    |
| Test       | 10,000 | 0–9    |

Each image is a single channel (grayscale), normalized to pixel values in `[0, 1]`.

## Requirements

- Python 3.9+
- PyTorch (or TensorFlow — adjust commands below)
- NumPy

```bash
pip install torch torchvision numpy
```

## Project Structure

```
MNIST/
├── README.md
├── train.py          # Training script
├── evaluate.py       # Evaluation on test set
├── model.py          # Model definition
└── data/             # Downloaded MNIST files (optional cache)
```

## Usage

**Train a model**

```bash
python train.py
```

**Evaluate on the test set**

```bash
python evaluate.py
```

## Model

A typical baseline is a small convolutional neural network (CNN):

- Conv layers to extract spatial features from digit strokes
- Pooling to reduce spatial dimensions
- Fully connected layers for classification into 10 classes

Expected test accuracy with a simple CNN: **~98–99%**.

## Results

| Model | Test Accuracy | Notes |
|-------|---------------|-------|
| —     | —             | Add results after training |

## References

- LeCun, Y., Cortes, C., and Burges, C.J.C. [The MNIST Database](http://yann.lecun.com/exdb/mnist/)
- [PyTorch MNIST tutorial](https://pytorch.org/tutorials/beginner/basics/quickstart_tutorial.html)

## License

MIT (or specify your license here)
