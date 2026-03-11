---
layout: page
title: "ConvPEFT: Adapting Transformer PEFT to CNN-based Audio Classification"
description: Systematic adaptation of LoRA and Adapter PEFT methods from Transformers to CNN architectures for on-device audio classification (UrbanSound8K)
img: #
importance: 5
category: research
related_publications: false
---

## ConvPEFT: Adapting Transformer PEFT to CNN-based Audio Classification

**Jiyoon Kim, Jaewon Mun, Woorim Shin | Ewha Womans University, Dept. of Computer Science and Engineering**

<div class="col-sm mt-3 mt-md-0">
    <a href="{{ site.baseurl }}/assets/pdf/ML%20Poster%20-%20Transformer%20to%20CNN(A1_%207016x9933).pdf" target="_blank" class="btn btn-primary">
        Research Poster (PDF)
    </a>
</div>

### Overview

Parameter-Efficient Fine-Tuning (PEFT) methods such as LoRA and Adapter were originally designed for Transformer architectures. This project systematically adapts them to CNN-based audio classification, proposing **Conv-LoRA** and **Conv-Adapter** as novel variants that preserve spatial structure in convolutional layers.

The motivation is practical: deploying high-accuracy audio classifiers (e.g., for hearing-impaired users in on-device environments) requires efficient fine-tuning with minimal trainable parameters.

### Methods

**Conv-LoRA**

- Adapts LoRA's low-rank decomposition to Conv2D layers
- Matrix A: 3×3 conv preserves spatial information; Matrix B: 1×1 pointwise conv for channel projection
- Δ W(x) = Conv_B(Conv_A(x))

**Conv-Adapter**

- Adapts sequential bottleneck structure to Conv2D layers
- Down-project → ReLU → Up-project with residual connection
- Serial insertion after main convolution layer

### Experiment Setup

- **Dataset**: UrbanSound8K — 8,732 audio clips across 10 urban sound classes
- **Input**: MFCC spectrograms (40×174×1)
- **Base Model**: 3-convolutional-layer CNN; Conv1 frozen, PEFT modules added to Conv2–3
- **Evaluation**: 10-fold cross-validation

### Key Results

| Method           | Trainable Params   | Accuracy   |
| ---------------- | ------------------ | ---------- |
| Scratch          | 110,474 (100%)     | 52.45%     |
| Full Fine-Tuning | 110,474 (100%)     | 59.38%     |
| Conv-LoRA        | 26,250 **(23.8%)** | 60.69%     |
| Conv-Adapter     | 38,570 **(34.9%)** | **62.01%** |

- Conv-Adapter achieves the **best accuracy (62.01%)**, outperforming Full Fine-Tuning with 65.1% fewer parameters
- Conv-LoRA delivers the **best parameter efficiency (23.8%)** while still exceeding Full FT accuracy
- Both PEFT methods demonstrate that lightweight adaptation is viable for on-device CNN models

### Technologies

**Framework**: PyTorch, PEFT
**Architecture**: CNN with Conv-LoRA / Conv-Adapter modules
**Audio Processing**: MFCC spectrograms
**Dataset**: UrbanSound8K
