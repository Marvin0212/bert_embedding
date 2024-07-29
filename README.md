# Surrogate Data Generation for Personally Identifiable Information (PII)

## Overview

This project focuses on generating surrogate data for Personally Identifiable Information (PII) to ensure privacy while maintaining data utility. The method leverages BERT embeddings and a custom decoding approach to create semantically similar yet distinct surrogate data.

## Approach

### Contextualized BERT Embedding
1. **Embedding Generation**: Utilize BERT to obtain contextualized embeddings for PII entities.

### Custom Decoder: LSTM and BERT MLM Head
1. **LSTM and BERT MLM Head**:
    - Use an LSTM in conjunction with the pretrained BERT Masked Language Modeling (MLM) head to decode the BERT embeddings.
    - The LSTM unpacks the entire PII embedding and routes it to the MLM head to project it back to the vocabulary, enabling the generation of surrogate PII.
    - Since the MLM head is designed to decode single tokens, the LSTM facilitates the generation of a sequence of tokens.

## Training Corpus

- **NER Corpus**: The Named Entity Recognition (NER) corpus, CONLL, is used to train the LSTM model.

## Code References

### Model Usage on GraSCCO Corpus
- **Notebook**: `Bert_embedding.ipynb`
- **Description**: This notebook sets up the pipeline for generating a surrogate for a doctor's letter using BERT embeddings and the custom decoder.

### Training the LSTM BERT MLM Head Model
- **Notebook**: `NER_data.ipynb`
- **Description**: This notebook details the training process of the LSTM BERT MLM head model using the CONLL NER corpus.
