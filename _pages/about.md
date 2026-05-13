---
layout: about
title: about
permalink: /
subtitle: Undergraduate Student at <a href='https://www.ewha.ac.kr/'>Ewha Womans University</a>
nav: false

profile:
  align: right
  image: tokyo.jpeg # 나중에 이걸로 : profile.JPG
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>wrim0923@gmail.com</p>
    <p>Suwon, South Korea</p>

selected_papers: false # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: false # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

I am Woorim Shin, an undergraduate student of Computer Science and Engineering at Ewha Womans University in Seoul, South Korea.

I'm passionate about **Natural Language Processing**, **AI Systems**, and **Korean Language Technology**. My work spans the full arc from low-level measurement and systems engineering to large-scale model fine-tuning and NLP research — driven by a desire to _understand deeply and build precisely_.

**NLP & Speech**

- Architected and deployed a production **Korean lecture ASR system** at Hiconsy, fine-tuning Whisper Large-v3 (1.55B) via LoRA on 6× RTX 4090 GPUs with DeepSpeed ZeRO-2
- Diagnosed and resolved a previously unknown **infinite hallucination bug** in Whisper LoRA fine-tuning, reducing insertion errors by **20.7×** — being written up as a standalone research paper
- Designed and deployed NLP pipelines for **student sentiment analysis**, **educational Q&A classification**, and **Korean LLM benchmarking**

**AI Systems & Security**

- Co-first authored a paper on **energy attribution for AI workloads in shared resource environments**, demonstrating AI workloads consume **4.7–11× more energy** than traditional workloads under identical resource allocations — submitted to _Mathematics_, MDPI (SCIE), Feb. 2026
- Built **fcoinman**, a Linux server compromise detector in Rust — born from a real incident where my own server was breached; detects miners, rootkits, backdoor accounts, and C2 connections with a single static binary

Beyond research, I won **3rd place at the Ewha Startup Contest** (Nov. 2025) with SchedAI, and am an active member of **Google Developer Group on Campus (GDGoC) Ewha**.

Feel free to reach out for research collaborations, internship opportunities, or discussions about NLP and AI systems!
