# MTL-ArabicPropagandaDetection

A Multi-Task Learning framework for **Arabic propaganda detection**, where the main task is propaganda classification and the auxiliary tasks are **sentiment detection** and **emotion detection**.

This project investigates whether learning related affective signals can improve the detection of propaganda in Arabic text using a shared transformer-based architecture.

---

## Overview

Propaganda detection is an important task in Natural Language Processing, especially for understanding manipulative and persuasive language in news and media. In Arabic, this task is still underexplored compared to English.

This repository presents a **Multi-Task Learning (MTL)** approach for Arabic propaganda detection, where:

- **Main task:** Propaganda detection
- **Auxiliary task 1:** Sentiment classification
- **Auxiliary task 2:** Emotion classification

The model uses a **shared encoder** and **task-specific classification heads** to jointly learn these tasks.

---

## Objectives

The main goals of this project are:

- Detect whether an Arabic text contains propaganda
- Improve propaganda detection performance through multi-task learning
- Explore the relationship between propaganda, sentiment, and emotion
- Evaluate different task-weighting strategies for balancing the learning process

---

## Model Architecture

The framework is based on a transformer encoder (e.g., **AraBERT**) followed by separate classification heads for each task.

### Architecture summary

- **Shared encoder:** Pretrained Arabic language model
- **Task-specific heads:**
  - Propaganda classification head
  - Sentiment classification head
  - Emotion classification head

The total loss is computed as a weighted combination of the three task losses.

---

## Tasks

### 1. Propaganda Detection
Binary classification:

- `Propaganda`
- `Non-Propaganda`

### 2. Sentiment Detection
Typical sentiment labels:

- `Positive`
- `Negative`
- `Neutral`

### 3. Emotion Detection
Typical emotion labels:

- `Happy`
- `Sad`
- `Anger`
- `Fear`
- `Non-emotion`

> Note: The exact labels may depend on the dataset version used in your experiments.

---

## Dataset

The dataset used in this work was developed in collaboration with the **King Salman Global Academy for Arabic Language**.  
All rights are reserved by the Academy, and the dataset must be requested directly from them.

If you use another dataset or a private version for experimentation, please describe it clearly in this section.

### Expected data format

Each sample may include:

- `text`
- `propaganda_label`
- `sentiment_label`
- `emotion_label`

Example:

{
  "text": "هذا القرار العظيم يثبت مرة أخرى أن قيادتنا الحكيمة وحدها القادرة على إنقاذ الوطن من الفوضى.",
  "propaganda_label": 1,
  "sentiment_label": "positive",
  "emotion_label": "happy"
}
