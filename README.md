# Text Summarization(LLMS)

## Overview
This project explores the development of a text summarization model using the `facebook/bart-large-cnn` transformer. It covers the full pipeline from dataset preparation to model training, evaluation, and generating summaries for unseen data.

## Key Components

- **Dataset Handling:** Loading and preprocessing the SAMSum dataset for dialogue summarization.
- **Text Tokenization:** Preparing text inputs with tokenization for model training.
- **Transformer Model Training:** Fine-tuning the `facebook/bart-large-cnn` model using the Hugging Face Trainer API.
- **Evaluation and Performance Metrics:** Assessing model accuracy and loss on the test dataset.
- **Inference and Summarization:** Using the trained model to summarize new dialogues.

## Implementation Details

### 1. Dataset Preparation

- **Loading Data:** The SAMSum dataset is imported using Hugging Face's datasets library.
- **Visualizing Samples:** Sample dialogues and summaries are displayed to understand the dataset structure.
- **Tokenization:** Text inputs are tokenized using the BART tokenizer with truncation and padding.

### 2. Preprocessing

- **Data Splitting:** The dataset is divided into training and validation sets.
- **Text Normalization:** Tokenized text inputs are formatted for model compatibility.

### 3. Model Architecture

- **Pre-trained Model:** Uses `facebook/bart-large-cnn`, a transformer-based summarization model.
- **Fine-tuning Setup:** The model is fine-tuned with a sequence-to-sequence objective.
- **Loss Function:** Categorical cross-entropy loss is used to optimize text generation.

### 4. Model Compilation and Training

- **Optimizer and Learning Rate Scheduling:** Uses Adam optimizer with weight decay.
- **Training Process:** The model is trained over 1 epoch with a batch size of 4.
- **Performance Tracking:** Training and validation loss are plotted for visualization.

### 5. Model Evaluation

- **Test Set Evaluation:** The model's performance is assessed using evaluation metrics like ROUGE.
- **Prediction Comparison:** Generated summaries are compared with reference summaries.

### 6. Making Predictions

- **Batch Predictions:** The model predicts summaries for unseen dialogues.
- **Text Generation:** Summarization is performed with a max length of 150 and min length of 50.
