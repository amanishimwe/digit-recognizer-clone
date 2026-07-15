# MNIST Handwritten Digit Classification

From-scratch NumPy neural network trained on the [Kaggle Digit Recognizer](https://www.kaggle.com/c/digit-recognizer) competition (MNIST-style 28×28 grayscale digits, labels 0–9).

## Overview

The notebook `main.ipynb`:

1. Loads competition data (download once via the Kaggle API)
2. Splits training data into train / validation
3. Trains a 2-layer network (ReLU + softmax) with mini-batch gradient descent
4. Visualizes predictions and writes a Kaggle `submission.csv`

## Requirements

- Python 3.9+
- A Kaggle account and API token ([create one here](https://www.kaggle.com/settings))

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Secrets

Do **not** commit API tokens.

Set your token in the environment, or keep it in a local `.config` file that is gitignored:

```bash
export KAGGLE_API_TOKEN="your_token_here"
```

Or create `.config` locally:

```
KAGGLE_API_TOKEN = "your_token_here"
```

If this token was ever committed to git, revoke it on Kaggle and create a new one.

## Project structure

```
MNIST/
├── README.md
├── requirements.txt
├── main.ipynb          # data load, train, evaluate, submit
├── .config             # local secrets only (gitignored)
└── data/               # downloaded CSVs (gitignored)
```

## Usage

Open and run `main.ipynb` top to bottom.

Expected validation accuracy with the default settings: roughly **90%+** (simple dense net; a CNN would score higher).

## Model

- Input: 784 flattened pixels, scaled to `[0, 1]`
- Hidden layer: 128 units, ReLU, He initialization
- Output: 10-way softmax
- Loss: cross-entropy (via softmax + one-hot targets)
- Optimizer: mini-batch SGD

## References

- LeCun, Y., Cortes, C., and Burges, C.J.C. [The MNIST Database](http://yann.lecun.com/exdb/mnist/)
- [Kaggle Digit Recognizer](https://www.kaggle.com/c/digit-recognizer)

## License

MIT
