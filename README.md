# Abstractive Text Summarization - Encoder-Decoder with Attention Mechanism

## Overview

This project implements an **Abstractive Text Summarization** system using an **LSTM-based Seq2Seq Encoder-Decoder model** with an **Attention Mechanism**. The model is designed to summarize lengthy articles into concise highlights, making it suitable for tasks like summarizing news articles or other long-form content. 

The model was trained on the **CNN/Daily Mail dataset**, a widely-used benchmark for summarization tasks. It achieved a BLEU score of **0.38**, indicating decent performance in generating summaries that closely align with the ground truth. Pre-trained **GloVe embeddings** were used to enrich the word representation and improve the model's understanding of the text.

## Dataset

The project primarily uses the **CNN/Daily Mail dataset**, processed by Nallapati et al. (2016). This dataset contains online news articles paired with multi-sentence summaries. The average article length is 781 tokens, and the average summary length is 56 tokens.

The dataset includes:
- **287,226 training pairs**
- **13,368 validation pairs**
- **11,490 test pairs**

## Key Features

- **LSTM-based Encoder-Decoder Architecture**: This Seq2Seq model encodes the input text and decodes it into a summary.
- **Attention Mechanism**: Helps the model focus on the most important parts of the input sequence, improving summary generation.
- **Pre-trained GloVe Embeddings**: These embeddings provide rich semantic information, improving the model’s understanding of the input text.
- **Evaluation**: The model's performance is evaluated using the **BLEU score** and **Cosine Similarity** to measure how well the predicted summaries align with the original summaries.

## Model Architecture

The model architecture consists of:
1. **Encoder**: Three stacked LSTM layers with dropout, which encode the input article into a fixed-length context vector.
2. **Decoder**: A single LSTM layer initialized with the encoder’s states to generate the summary.
3. **Attention Layer**: A custom attention mechanism that helps the decoder focus on the relevant parts of the input article.
4. **Dense Layer**: This final layer is used to generate the predicted summary.

## Training and Results

The model was trained for 30 epochs, using the **Adam optimizer** and **sparse categorical cross-entropy loss**. During training, we utilized **early stopping** and **model checkpointing** to ensure the best-performing model was saved.

**BLEU Score**: The model achieved a BLEU score of **0.38** on the CNN/Daily Mail test set.

## Evaluation

The model’s performance was also tested using Cosine Similarity with **Universal Sentence Encoder**. This provided insights into the semantic similarity between the predicted and actual summaries, complementing the BLEU score evaluation.
