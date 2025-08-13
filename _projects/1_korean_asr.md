---
layout: page
title: Korean Educational ASR System
description: Advanced speech recognition system fine-tuned for Korean educational content using Whisper Large-v3 with LoRA
img: assets/img/1.jpg
importance: 1
category: ai
related_publications: false
---

## Overview

Developed a sophisticated Korean Automatic Speech Recognition (ASR) system specialized for educational content by fine-tuning OpenAI's Whisper Large-v3 model using LoRA (Low-Rank Adaptation) techniques.

## Key Features

- **Fine-tuned Whisper Model**: Adapted OpenAI Whisper Large-v3 specifically for Korean educational lectures
- **Custom Tokenization**: Built domain-specific 8,000-vocabulary SentencePiece tokenizer optimized for Korean educational terms
- **RAG Pipeline**: Implemented 4-stage Retrieval-Augmented Generation pipeline for post-processing
- **Multi-GPU Training**: Utilized distributed training with DeepSpeed ZeRO-2 across 6x RTX 4090 GPUs

## Technical Achievements

- **275% improvement** in segmentation precision (833 → 2,288 segments)
- **55.6% efficiency improvement** with custom tokenizer
- **2.3x faster processing** with domain-specific vocabulary optimization
- **68.3% reduction** in average segment length (5.02s → 1.59s)

## Technologies Used

- **Deep Learning**: PyTorch, Transformers, PEFT, LoRA
- **Infrastructure**: DeepSpeed, Flash Attention 2.5.8
- **NLP**: Korean sentence transformers, FAISS vector search
- **Post-processing**: Google Gemini 2.5 Flash, PMI-based term extraction

## Impact

This project demonstrates advanced ML engineering skills and research methodology, showcasing the ability to adapt state-of-the-art models for specific linguistic and domain requirements.