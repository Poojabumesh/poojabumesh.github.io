---
title: "Building an AI-Powered Search with RAG, OpenAI, and Pinecone"
layout: post
date: 2025-07-30
categories: [LLMs, RAG, NLP]
tags: [OpenAI, Pinecone, AWS, HuggingFace, RAG, Lambda]
author: poojabumesh
---

# Enhancing Product Search with AI: My Internship Experience

During my internship as a Machine Learning Engineer at a fast-paced e-commerce startup, I worked on building a semantic search and recommendation system to improve product discovery in a large catalog. 

---

## Objective

The primary objective of my internship project was to **enhance product search and retrieval** using AI.
Traditional keyword-based search often produced irrelevant results, making it difficult for users to quickly find what they needed.

Our goal was to:

1. **Understand user intent** beyond simple keyword matching.
2. **Retrieve semantically relevant products** from a large catalog using embeddings.
3. **Rerank results** to present the most meaningful items first.

By combining **machine learning, vector embeddings, and LLM-based reranking,** we aimed to create a system that significantly improved user search experience.

---

## Design
<p align="center">
  <img src="/assets/images/semantic_search.png" alt="High-level system diagram" style="max-width:100%;" />
</p>


The system architecture was modular and consisted of the following components:
1. **Intent Classification**
  - Categorized incoming queries as:
    - **Recommendation** (e.g., “Suggest a fruity red wine”)
    - **Informational** (e.g., “What is a Pinot Noir?”)
    - **Conversational** (e.g., “I need a wine for dinner tonight”)
  - Guided the downstream retrieval and reranking logic.

2. **Vector-Based Retrieval**
  - Embedded all product attributes into a **semantic vector space** using **sentence transformers.**
  - Retrieved top candidate products using **cosine similarity** on **Pinecone vector database.**

3. **Reranking Layer**
  - Applied **LLM-powered reranking** (via Cohere Reranker) to refine the top results.
  - Focused on **contextual relevance** to the query.

4. **Duplicate Filtering**
  - Used **Levenshtein distance** and semantic checks to remove near-duplicate products.
  - Ensured cleaner, more diverse search results.

5. Deployment
  - Deployed as a **serverless pipeline** using **AWS Lambda**, integrating Pinecone and third-party APIs for reranking.
  - Designed for low-latency response in a real-time user interface

---

## Data Processing
The data processing workflow was critical to enable semantic search:

- **Product Embeddings**  
  - Curated titles, descriptions, and attributes for thousands of products  
  - Generated **dense embeddings** with a pre-trained transformer  

- **Query Pre-processing**  
  - Normalized, tokenized, and embedded user queries in the same vector space  
  - Enabled direct **semantic similarity** comparisons between queries and products.  

- **Filtering & Cleaning**  
  - Applied post-processing to remove repetitive, low-quality, or near-identical results.
  - Optimized embeddings for **efficient vector search** in Pinecone.

---

## Optimization

Performance optimization was a key focus to ensure a smooth user experience:
1. **Latency Reduction**
  - Streamlined API calls and restructured the pipeline.
  - Reduced **end-to-end response time** from **~2 minutes to under 30 seconds.**

2. **Prompt Engineering**
  - Tuned LLM prompts for **contextual reranking.**
  - Improved semantic relevance and reduced ambiguous results.

3. **Deduplication Logic**
  - Integrated **string-based** and **semantic similarity scoring.**
  - Prevented duplicate or visually identical products in top recommendations.

---

## Evaluation

To ensure the system was effective and robust:
1. **Custom Evaluation Dataset**
  - Created a test set of **~250 diverse queries** representing real user intent.
  - Used this for regression testing during iteration.

2. **Manual Review**
  - Performed **visual inspection** of top results for subjective relevance.
  - Collected feedback from the team to improve reranking logic.

3. **Embedding Similarity Analysis**
  - Leveraged **CLIP-based similarity scores** to evaluate alignment between product images and query intent.

---

## Key Takeaways

This project was a complete **end-to-end ML experience** :  from **data processing** and **semantic retrieval** to **latency optimization** and **evaluation in production**.

I learned how to:
  - Build hybrid search systems combining embeddings and LLMs.
  - Optimize for both accuracy and latency in production ML pipelines.
  - Use vector databases and serverless architectures for scalable deployment.

This experience strengthened my skills in **machine learning engineering, MLOps,** and **semantic search**, while demonstrating how data science and domain knowledge can work together to improve user experience.
