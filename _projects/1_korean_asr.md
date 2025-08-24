---
layout: page
title: AI subtitle generation model for Korean educational content at Hiconsy
description: Advanced speech recognition system fine-tuned for Korean educational content using Whisper Large-v3 with LoRA
img: #
importance: 1
category: ai
related_publications: false
---
## Korean Educational ASR System Development  
> *This repository is kept private due to Hiconsy's confidentiality requirements.*  
> *However, you can review the project results and documentation via my guidelines for subtitle reviewers [here](https://nonstop-pike-0e5.notion.site/25890cb97b1e809386a9d5e71f524df7?source=copy_link).*

### Project Documentation
<div class="col-sm mt-3 mt-md-0">
    <a href="{{ site.baseurl }}/assets/pdf/250805 Comparison test - Comparison.pdf" target="_blank" class="btn btn-primary">
        📄 Interim Report - Model Comparison Test (PDF)
     </a>
</div>

### Overview  
Led the end-to-end development of a Korean Automatic Speech Recognition (ASR) system for educational content of 시대인재 at Hiconsy, diving deep into the entire ML pipeline from model fine-tuning to deployment. This project became my gateway into advanced AI engineering and sparked my passion for MLOps.

### What I Built  
- **Fine-tuned Whisper Model**: Adapted OpenAI Whisper Large-v3 for Korean educational lectures using LoRA techniques
- **Custom Tokenization Pipeline**: Developed domain-specific 8,000-vocabulary SentencePiece tokenizer optimized for Korean educational terminology
- **4-Stage RAG System**: Implemented Retrieval-Augmented Generation pipeline for intelligent post-processing
- **Distributed Training Setup**: Configured multi-GPU environment with DeepSpeed ZeRO-2 across 6x RTX 4090 GPUs

### Key Learnings & Results
Through this project, I gained hands-on experience in:
- **Model Engineering**: PyTorch, Transformers, PEFT, LoRA implementation
- **Infrastructure Management**: DeepSpeed optimization, Flash Attention configuration  
- **NLP Engineering**: Korean embeddings, FAISS vector search, custom tokenizers
- **Automation & MLOps**: Google Apps Script for evaluation pipelines, Tensorboard monitoring
- **Project Leadership**: Coordinating review processes and managing development workflows

**Measurable Impact:**
- **275% improvement** in segmentation precision (833 → 2,288 segments)
- **55.6% efficiency gain** with custom tokenizer
- **2.3x faster processing** through domain optimization
- **68.3% reduction** in average segment length (5.02s → 1.59s)

### Technologies Explored
**Core Stack**: PyTorch, Transformers, PEFT, LoRA, DeepSpeed  
**NLP Tools**: Korean sentence transformers, FAISS, SentencePiece  
**Infrastructure**: Multi-GPU training, Flash Attention 2.5.8  
**Post-processing**: Several LLM models like OpenAI's GPT, Google Gemini.

### What This Project Taught Me
This experience transformed my understanding of AI engineering and ignited my curiosity about MLOps, distributed systems, and production-ready ML pipelines. It showed me how theoretical knowledge translates into solving real-world problems – exactly the kind of work I want to pursue as I continue growing in this field.