# Text Summarizer (T5 Transformer)

This project is a text summarization web application built with FastAPI, Jinja2, and a fine-tuned Hugging Face `t5-small` model. It accepts long-form input text, cleans it, runs transformer-based inference, and returns a shorter abstractive summary through both a browser UI and a REST API.

## Live Demo
https://text-summarizer-pxx8.onrender.com/

## Project Overview

The goal of this project is to make long text easier to understand quickly. Instead of extracting a few lines directly from the original content, the model generates a new condensed version that captures the main meaning in fewer words.

This repository includes:

- A FastAPI backend for serving the model
- A simple web interface for entering text and viewing summaries
- A local saved transformer model inside `saved_summary_model`
- Basic preprocessing and device selection for CPU, CUDA, or Apple MPS

## Key Features

- Transformer-based abstractive summarization using a fine-tuned `t5-small` model
- FastAPI application with a clean API endpoint
- Browser-based frontend using Jinja2 templates and static CSS
- Automatic device selection for `cpu`, `cuda`, or `mps`
- Local model loading from the repository without needing to download model weights at runtime

## How It Works

1. The user enters or pastes text into the web interface.
2. The frontend sends the text to the `/summarize/` endpoint as JSON.
3. The backend cleans the input by removing extra whitespace and HTML tags.
4. The tokenizer converts the text into model inputs.
5. The T5 model generates a summary using beam search.
6. The generated tokens are decoded and returned to the user.

## Tech Stack

- Python `3.10.20`
- FastAPI
- Uvicorn
- Hugging Face Transformers
- PyTorch
- Jinja2
- HTML, CSS, and vanilla JavaScript
