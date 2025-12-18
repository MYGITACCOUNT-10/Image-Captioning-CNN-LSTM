# Image Caption Generation using CNN–LSTM

## Overview
This project implements an end-to-end image captioning system that automatically generates textual descriptions for images. The model follows an encoder–decoder architecture, where a pretrained Convolutional Neural Network (CNN) extracts visual features and an LSTM-based decoder generates captions word by word.

## Objective
The goal of this project is to design, train, and evaluate a deep learning model capable of generating meaningful captions for images using a custom dataset.

## Dataset
The dataset consists of images paired with their corresponding captions. Each image may have one or more captions describing its visual content. The dataset is divided into training, validation, and test sets.

Each record contains:
- Image filename
- Caption text

## Model Architecture
The model uses a CNN–LSTM encoder–decoder architecture:
- **Image Encoder:** A pretrained CNN extracts 2048-dimensional feature vectors from images.
- **Text Decoder:** An embedding layer followed by an LSTM processes partial captions and predicts the next word.
- **Output Layer:** A dense layer with softmax activation predicts the next word from the vocabulary.

## Training Strategy
- Captions are tokenized using a TextVectorization layer.
- Teacher forcing is used during training.
- Training is performed using a `tf.data.Dataset` pipeline for memory efficiency.
- Sparse categorical cross-entropy loss and word-level accuracy are used as evaluation metrics.
- Training was limited to 5 epochs to ensure stable dataset iteration.

## Evaluation
Model performance is evaluated using:
- Training and validation loss curves
- Word-level accuracy
- Qualitative analysis by generating captions for unseen images

Sudden fluctuations in accuracy or loss are expected due to varying caption complexity and dataset imbalance.


## Limitations
- The model uses greedy decoding, which may produce repetitive or generic captions.
- No attention mechanism is implemented.
- Caption quality is influenced by dataset bias and vocabulary distribution.

## Future Improvements
- Add attention mechanism
- Implement beam search decoding
- Evaluate using BLEU or CIDEr metrics
- Fine-tune the CNN encoder

  ## How to Run
1. Install dependencies using:
2. Open the notebook and run all cells sequentially.
3. Update dataset paths if required.

## Technologies Used
- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Matplotlib







