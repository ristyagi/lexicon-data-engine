# 🚀 AI-Driven Lexicon Data Engine
**A Self-Sustaining Linguistic Data Product & Interactive Learning Portal**

[![Live Demo](https://img.shields.io/badge/Live-Demo-brightgreen)](https://ristyagi.github.io/lexicon-data-engine/)
[![Stack-Python](https://img.shields.io/badge/Stack-Python-blue)](https://www.python.org/)
[![Stack-GeminiAI](https://img.shields.io/badge/AI-Gemini_Pro-orange)](https://deepmind.google/technologies/gemini/)

## 📌 Project Overview
This project is designed as a **decoupled data pipeline** that automates the collection, enrichment, and visualization of English-Hindi vocabulary. Unlike a static dictionary, this engine uses GenAI to perform feature engineering (generating meanings, examples, and difficulty levels) and serves it through a serverless frontend.

### Key Capabilities:
* **Automated ETL Pipeline:** Python-based ingestion that transforms raw words into structured JSON.
* **GenAI Enrichment:** Integrated Google Gemini API for semantic data generation.
* **Medallion Architecture:** Follows a structured data flow (Bronze: Raw Input → Silver: Validated Data → Gold: Optimized JSON).
* **Interactive UI:** A React-style Vanilla JS frontend featuring a **Flashcard Game** and **Alphabetical Index**.

---

## 🏗️ Architectural Design (Principal Data Engineer Lens)



1.  **Source:** User appends a word to the input queue.
2.  **Orchestration:** GitHub Actions triggers a Python-based worker.
3.  **Processing (Compute):** The Python script calls Gemini Pro to fetch linguistic metadata.
4.  **Data Quality:** Schema validation ensures no null values and enforces difficulty tagging.
5.  **Serving:** A "Gold" JSON file is pushed to the repo, triggering a serverless deployment via GitHub Pages.

---

## 🛠️ Tech Stack
* **Language:** Python (Data Processing), JavaScript (Frontend)
* **AI:** Google Gemini Pro API
* **Storage:** JSON-based Flat File Database
* **Infrastructure:** GitHub Pages (Serverless Hosting)
* **CI/CD:** GitHub Actions (Data Orchestration)
* **Styling:** Tailwind CSS

---

## 📊 Data Schema
The "Gold" dataset is stored in `data/words.json` with the following schema:

```json
{
  "word": "Serendipitous",
  "meaning": "Lucky in making unexpected and fortunate discoveries.",
  "hindi_meaning": "आकस्मिक रूप से लाभ देनेवाला",
  "difficulty": "Medium",
  "example1": "Our meeting was entirely serendipitous.",
  "example2": "The discovery of Penicillin was serendipitous."
}
