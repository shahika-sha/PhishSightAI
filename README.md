# PhishSight AI 🔍

**Explainable NLP-based Phishing & Scam Detection with Visual Attention Assist**

PhishSight AI is a multi-channel phishing detection system that protects users across emails, SMS, and web pages. Unlike traditional spam filters that act as black boxes, it explains *why* content is flagged — highlighting risky words and URL patterns — while nudging users to check sender details and URLs before clicking.

## 🚩 Problem

Phishing attacks bypass traditional filters by exploiting urgency, spoofed domains, and social engineering. Most existing tools give a simple safe/unsafe label with no explanation, leaving non-technical users unable to learn from or trust the decision.

## ✅ What It Does

- Detects phishing across **email, SMS, and web pages** in real time via a Chrome extension
- Explains every prediction using **LIME and SHAP**, highlighting the exact words or URL features that triggered a flag
- Uses an optional **gaze-tracking module** to check whether users look at the URL bar/sender line before interacting with risky content, and nudges them if they don't
- Learns continuously from user feedback ("Mark as Safe/Scam") through a retraining pipeline

## 🏗️ Architecture

1. **Chrome Extension** (Manifest V3) — captures page/email/SMS content and URLs
2. **FastAPI Backend** — cleans and tokenizes text, extracts URL features, runs ML classifiers
3. **Explainability Layer** (LIME/SHAP) — surfaces risky tokens and generates plain-language tips
4. **Database + Retraining Pipeline** — logs predictions and feedback, periodically retrains models

## 🛠️ Tech Stack

- **Frontend:** HTML, CSS, JavaScript, Chrome Extension (Manifest V3)
- **Backend:** Python, FastAPI
- **ML/NLP:** scikit-learn, spaCy, NLTK, Transformers/BERT, LIME, SHAP
- **Database:** MySQL / SQLite
- **Gaze Tracking:** WebGazer.js

## 📊 Performance

| Channel | Accuracy | Precision | Recall | Avg. Response |
|---|---|---|---|---|
| Email | 95.2% | 94.8% | 95.6% | 1.4s |
| SMS | 94.7% | 93.9% | 95.1% | 1.2s |
| Web/URL | 96.1% | 95.4% | 96.8% | 1.7s |

Tested on public datasets (UCI Phishing Websites, PhishTank URLs, SpamAssassin emails) plus synthetic SMS samples reflecting Indian smishing patterns.

## 🌟 What Makes It Different

Most prior systems (Hernandes 2021, Pavani et al. 2024, Alam 2024, Yakandawala 2024) handle only URLs or only emails, use a single explainability method, and have no behavioral or feedback layer. PhishSight AI is the only system combining:
- Multi-channel coverage (email + SMS + web)
- Dual explainability (SHAP + LIME)
- Gaze-based behavioral nudging
- A live feedback-driven retraining loop

## 🚀 Future Enhancements

- Multilingual detection (mBERT, XLM-RoBERTa) for regional and code-switched scams
- Detection of QR-code phishing, OCR-based image scams, and deepfake audio/video
- Adversarial red-teaming using reinforcement learning to harden the models
- Native mobile app for Android/iOS
- Microservices-based backend for enterprise-scale deployment

## 👥 Team

Built as a final-year B.Tech capstone project (AI & Data Science) at M.I.E.T. Engineering College, Trichy — by Afiga Begum A, Noorul Hasna A, Shahika S, and Sowmiya R.

---

*This project was developed as an academic capstone and is not currently under active development.*
