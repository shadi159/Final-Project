# Recognition Changes in Social State Resting upon Arabic Media

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)
![NLP](https://img.shields.io/badge/NLP-Arabic-success.svg)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen.svg)

## 📌 Project Overview
This project presents an automated, quantitative analytical pipeline designed to monitor and mathematically model the dynamic Arabic mass media landscape on social networks (specifically X/Twitter). Focusing on the Israel-Gaza conflict, the system aims to expose discrete linguistic markers that signal structural changes in public discourse connected to geopolitical and security fluctuations.

By bridging the gap between traditional journalism analysis and modern social media mining, the software acts as a "real-time social mirror," filtering out platform noise to identify significant narrative ruptures and distinct historical phases.

## ⚙️ System Architecture & Pipeline
The solution is architected as a sequential data processing pipeline, heavily utilizing Natural Language Processing (NLP), statistical feature selection, and unsupervised machine learning:

1. **Arabic NLP Normalization (Stage 2):** Cleans highly unstructured Arabic tweets by stripping URLs, mentions, hashtags, and diacritics (Tashkeel) while unifying complex character variants.
2. **N-gram Extraction (Stage 3):** Extracts character-level trigrams to implicitly capture Arabic morphological roots without relying on external grammatical dictionaries.
3. **Dimensionality Reduction (Stage 4):** Employs the Normalized Median (V1) metric to filter out transient social media noise, reducing a raw vocabulary of ~37,000 N-grams to ~1,000 highly stable features.
4. **Temporal Dependency Tracking (Stage 5):** Computes the Mean Rank Dependency (ZVT) using Spearman's rank correlation over a 7-day retrospective memory window to generate a continuous stability signal.
5. **Change Point Detection (Stage 6):** Applies a Haar Discrete Wavelet Transform (DWT) via grid-search optimization to smooth the signal and pinpoint exact dates of narrative ruptures.
6. **Segment-Aware Phase Clustering (Stage 7):** Partitions the timeline into contiguous historical phases using a segment-aware feature matrix and KMeans clustering.

## 📊 Key Results
* **High-Fidelity Detection:** Successfully pinpointed major real-world events, including the October 2023 outbreak and the November 2023 ceasefire, directly from the linguistic data.
* **Algorithm Optimization:** Optimized Haar Wavelet approximation (Level 3, Threshold 0.30) achieved a Pearson correlation of ~0.969 with the raw signal.
* **Contiguous Clustering:** Segment-aware KMeans (k=5) completely eliminated temporal fragmentation, achieving a high Silhouette score of 0.8037.
* **Robust Validation:** Passed a comprehensive 48-stage test suite covering unit, integration, and synthetic ground-truth validations.

## 🚀 Getting Started

### Prerequisites
* Python 3.8+
* Libraries: `pandas`, `numpy`, `scipy`, `scikit-learn`, `PyWavelets`, `pyarabic`, `matplotlib`

## 👥 Authors & Credits
Shadi Alkeesh
Ayman Haj
Academic Supervisors:
Dr. Renata Avros
Prof. Zeev Volkovich
Institution: ORT Braude College of Engineering (Software Engineering Department).
