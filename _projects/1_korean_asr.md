---
layout: page
title: Korean CSAT Lecture ASR Customization System
description: Production-grade speech recognition system fine-tuned for Korean CSAT lectures using Whisper Large-v3, LoRA, and DeepSpeed ZeRO-2
img: #
importance: 1
category: ai
related_publications: false
---

## Korean CSAT Lecture ASR Customization System

**Jun. 2025 – Feb. 2026 | PyTorch, HuggingFace, LoRA, DeepSpeed, Optuna | Independent Developer**

> _This repository is kept private due to Hiconsy's confidentiality requirements._ > _However, you can review the project results and documentation via my guidelines for subtitle reviewers [here](https://nonstop-pike-0e5.notion.site/25890cb97b1e809386a9d5e71f524df7?source=copy_link)._

### Project Documentation

<div class="col-sm mt-3 mt-md-0">
    <a href="{{ site.baseurl }}/assets/pdf/250805 Comparison test - Comparison.pdf" target="_blank" class="btn btn-primary">
        📄 Interim Report - Model Comparison Test (PDF)
     </a>
</div>

### Overview

Engineered a specialized end-to-end Automatic Speech Recognition system to generate highly accurate subtitles for Korean CSAT (College Scholastic Ability Test) lectures at Hiconsy. As the sole developer, I owned the entire ML pipeline from model architecture decisions to production deployment and QA automation.

### What I Built

- **Fine-tuned Whisper Large-v3 (1.55B)**: Adapted via LoRA using a custom Korean education tokenizer; authored a distributed training script on 6× RTX 4090 GPUs with DeepSpeed ZeRO-2
- **Custom Tokenization Pipeline**: Developed domain-specific 8,000-vocabulary SentencePiece tokenizer optimized for Korean CSAT terminology
- **Hallucination Bug Fix**: Independently diagnosed and resolved a severe infinite hallucination bug native to Whisper LoRA fine-tuning by decoupling PAD/EOS tokens — reducing insertion errors by **20.7×** (drafted as a standalone research paper)
- **Serverless QA Automation Layer**: Built using Google Apps Script enabling automated SRT parsing, timestamp alignment, and role-based access control to accelerate the data review process

### Key Results

- **20.7× reduction** in insertion errors via hallucination bug fix
- **275% improvement** in segmentation precision (833 → 2,288 segments)
- **55.6% efficiency gain** with custom tokenizer
- **68.3% reduction** in average segment length (5.02s → 1.59s)

### Technologies

**Core Stack**: PyTorch, Transformers, PEFT/LoRA, DeepSpeed ZeRO-2, Optuna
**NLP Tools**: Korean SentencePiece tokenizer, FAISS, Korean sentence transformers
**Infrastructure**: 6× RTX 4090 multi-GPU training, Flash Attention 2.5.8
**Automation**: Google Apps Script, Tensorboard monitoring
