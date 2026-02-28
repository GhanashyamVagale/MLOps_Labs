# LLM Data Pipeline Lab

Minimal data pipeline for preparing text data for GPT style language
model training using Hugging Face and PyTorch.

## Overview

This notebook demonstrates how to:

-   Load a small subset of the AG News dataset
-   Tokenize text using a GPT2 tokenizer
-   Concatenate and split tokens into fixed size blocks (128 tokens)
-   Create a PyTorch `DataLoader`
-   Prepare inputs and labels for causal language modeling


## Usage

Install dependencies:

``` bash
pip install datasets transformers torch
```

Open and run:

``` bash
jupyter notebook LLM_Data_pipeline.ipynb
```

Run all cells to generate tokenized batches ready for GPT style
training.

## Output

Each batch contains:

-   `input_ids`
-   `labels` (same as input for next token prediction)

Example batch shape:

    (8, 128)

-   Batch size: 8
-   Sequence length: 128 tokens


