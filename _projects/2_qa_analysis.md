---
layout: page
title: Educational Q&A Classification System for Korean CSAT
description: Dual-subject cognitive NLP taxonomy with GPT-3.5 Turbo fine-tuning and zero-shot GPT-4, classifying 720+ live student questions
img: #
importance: 4
category: ai
related_publications: false
---

## Educational Q&A Classification System for Korean CSAT

**Mar. 2025 – May 2025 | OpenAI GPT-4, GPT-3.5 Turbo (fine-tuning), Streamlit | Project Lead (Team of 4)**

### Project Documentation

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <a href="{{ site.baseurl }}/assets/pdf/Q&A-analysis-system.pdf" target="_blank" class="btn btn-primary">
            📄 Main Project Report (PDF)
        </a>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <a href="{{ site.baseurl }}/assets/pdf/2025Q2Seminar.pdf" target="_blank" class="btn btn-outline-primary">
            📋 Q2 Seminar Presentation (PDF)
        </a>
    </div>
</div>

### Overview

Led a team of 4 to design a dual-subject cognitive NLP taxonomy from scratch, bridging pedagogical theory with prompt engineering to categorize complex student question workloads from Sidaeinzae's TA app. The core challenge was transforming an inherently ambiguous classification problem (Korean literature) into a computationally tractable framework.

### What I Built

- **Dual-Subject NLP Taxonomy**: Designed 8-category classification framework (Q0–Q7) grounded in deep research into Korean and Math subject characteristics and student inquiry patterns
- **Fine-tuned GPT-3.5 Turbo**: Trained domain-specific model on custom-labeled educational Q&A dataset
- **Production Streamlit Dashboard**: Deployed real-time web application classifying **720+ live questions**, accelerating the QA team's response routing
- **Zero-shot GPT-4 Integration**: Combined fine-tuned and zero-shot approaches for optimal coverage across question types

### Key Results

- **720+ live questions** classified in production
- **Solved previously abandoned** Korean literature classification task
- **80% accuracy** on complex multi-subject question categorization
- Directly drove business content strategy through real-time routing

### Technologies

**AI/ML**: OpenAI GPT-4 (zero-shot), GPT-3.5 Turbo (fine-tuning)
**Web Development**: Streamlit, real-time data processing
**Visualization**: Plotly interactive dashboards
**Data Engineering**: Pandas, large-scale dataset labeling and processing
