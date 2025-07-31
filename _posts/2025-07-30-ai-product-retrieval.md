---
title: "Building an AI-Powered Wine Catalog Search with RAG, OpenAI, and Pinecone"
layout: post
date: 2025-07-30
categories: [LLMs, RAG, NLP, Internship]
tags: [OpenAI, Pinecone, AWS, HuggingFace, RAG, Lambda]
author: poojabumesh
---

## 🍷 Project Overview

As a Machine Learning Engineer Intern, I developed and deployed an intelligent product retrieval system for a wine e-commerce platform. The system combined **vector embeddings**, **LLM-powered search**, and **retrieval-augmented generation (RAG)** to enhance user experience through natural language interaction.

---

## 🎯 Objectives

- Enable users to ask product-related questions in natural language
- Improve semantic search relevance and reduce latency
- Integrate the solution into the live e-commerce platform

---

## ⚙️ Architecture & Components

**🔍 Query Understanding**
- Built an **intent classifier** to distinguish between:
  - Recommendation
  - Information-seeking
  - Conversational queries
- Applied **cosine similarity** and **Levenshtein distance** for fallback routing logic

**🧠 LLM Integration**
- Used **OpenAI GPT-4** for answer generation via Retrieval-Augmented Generation (RAG)
- Engineered prompts for UI formatting and dynamic instruction routing

**📦 Product Retrieval**
- Created vector embeddings from product attributes using sentence-transformers
- Indexed 10,000+ products in **Pinecone** (stored in S3)
- Added a Hugging Face **cross-encoder reranker** for result boosting
- Filtered near-duplicates for better diversity and precision

**🚀 Deployment**
- Deployed on **AWS Lambda**
- API orchestration between Pinecone, OpenAI, and Cohere Reranker
- Reduced average response time from **~2 minutes → <30 seconds**

---

## 📊 Evaluation & Monitoring

- Curated a dataset of **250+ diverse queries and expected responses**
- Built a baseline framework for continuous evaluation
- Used CLIP-style embeddings for internal similarity checks

---

## 💬 Impact

- Presented the project to the **Co-founder and CTO**
- Successfully integrated into the company’s e-commerce platform
- Enabled **real-time product recommendations** and **intelligent query handling**

---

## 🧩 Tools & Technologies

| Stack | Description |
|-------|-------------|
| 🧠 OpenAI | GPT-4 for answer generation |
| 📚 Pinecone | Vector DB for 10k+ embeddings |
| 🤗 Hugging Face | Cross-encoder for reranking |
| ☁️ AWS | Lambda, S3 for scalable deployment |
| 🔍 Cohere | Reranker via AWS Marketplace |
| 🧪 Custom Eval | Query-response benchmarking |

---

## 📁 Project Link

👉 [GitHub Repository](https://github.com/yourusername/wine-llm-rag-search)

---

## 💡 Key Takeaways

This project helped me deeply understand:
- How to combine symbolic logic and neural ranking
- Trade-offs between latency, relevance, and LLM cost
- The power of prompt engineering and evaluation frameworks in production AI systems
