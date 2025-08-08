---
title: "Building an AI‑Powered Search with RAG, OpenAI, and Pinecone"
layout: post
date: 2025-07-30
categories: [LLMs, RAG, NLP]
tags: [OpenAI, Pinecone, AWS, HuggingFace, RAG, Lambda]
author: poojabumesh
excerpt: "During my internship as a Machine Learning Engineer at a fast‑paced e‑commerce startup, I built a semantic search and recommendation system to improve product discovery in a large catalog."
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
---

<div class="blog-header" markdown="1">
# {{ page.title }}
<span class="blog-date">📅 {{ page.date | date: "%B %d, %Y" }}</span>  
<span class="blog-author">👩‍💻 {{ page.author }}</span>  
<span class="blog-tags">🏷️ {% for tag in page.tags %}<span class="tag">{{ tag }}</span>{% endfor %}</span>
</div>

<div class="blog-content" markdown="1">

## 🚀 Enhancing Product Search with AI: My Internship Experience

During my internship as a Machine Learning Engineer at a fast‑paced e‑commerce startup, I worked on building a semantic search and recommendation system to improve product discovery in a large catalog.

<div class="highlight-box">
💡 **Key Challenge:** Traditional keyword‑based search often produced irrelevant results, making it difficult for users to quickly find what they needed.
</div>

---

## 🎯 Objective

The primary objective of my internship project was to **enhance product search and retrieval** using AI.

### What We Set Out to Accomplish

<div class="objective-grid" markdown="1">
<div class="objective-card" markdown="1">
#### 🧠 Understand User Intent  
Go beyond simple keyword matching to understand what users really want.
</div>

<div class="objective-card" markdown="1">
#### 🔍 Semantic Retrieval  
Retrieve semantically relevant products from a large catalog using embeddings.
</div>

<div class="objective-card" markdown="1">
#### 📊 Smart Reranking  
Rerank results to present the most meaningful items first.
</div>
</div>

By combining **machine learning, vector embeddings, and LLM‑based reranking,** we aimed to create a system that significantly improved user search experience.

---

## 🏗️ Design

<div class="image-container">
  <img src="{{ '/assets/images/semantic_search.png' | relative_url }}" alt="System Architecture Diagram" class="blog-image" />
  <p class="image-caption"><em>System architecture showing the complete AI‑powered search pipeline</em></p>
</div>

### 🎭 1. Intent Classification

**Purpose:** Categorize incoming queries to guide downstream processing.

**Query Types:**

- 🛍️ **Recommendation** → “Suggest a fruity red wine”  
- ℹ️ **Informational** → “What is a Pinot Noir?”  
- 💬 **Conversational** → “I need a wine for dinner tonight”  

> **Impact:** Guides retrieval and reranking logic for better results.

### 🔢 2. Vector‑Based Retrieval

**Core Technology:** Semantic embeddings + vector similarity search

- Embedded all product attributes into a **semantic vector space** using **sentence transformers**  
- Retrieved top candidate products using **cosine similarity** on **Pinecone**  

> **Why This Works:** Captures meaning and context, not just keyword matches.

### 🎯 3. Reranking Layer

**Refinement Stage:** LLM‑powered contextual reranking

- Applied **LLM‑powered reranking** (via Cohere Reranker) to refine the top results  
- Focused on **contextual relevance** to the query  

> **Result:** Dramatically improved relevance of final search results.

### 🧹 4. Duplicate Filtering

**Quality Control:** Ensure clean, diverse results

- Used **Levenshtein distance** and semantic checks to remove near‑duplicate products  
- Delivered cleaner, more diverse search results  

### ☁️ 5. Deployment

**Serverless Architecture:** Scalable, cost‑effective deployment

- Deployed as a **serverless pipeline** using **AWS Lambda**, integrating Pinecone and third‑party APIs for reranking  
- Designed for low‑latency response in a real‑time UI  

---

## 📊 Data Processing

The data processing workflow was critical to enable semantic search:

<div class="process-grid" markdown="1">
<div class="process-card" markdown="1">
#### 📦 Product Embeddings  
* Curated titles, descriptions, and attributes for thousands of products  
* Generated **dense embeddings** with a pre‑trained transformer
</div>

<div class="process-card" markdown="1">
#### 🔍 Query Pre‑processing  
* Normalized, tokenized, and embedded user queries in the same vector space  
* Enabled direct **semantic similarity** comparisons between queries and products
</div>

<div class="process-card" markdown="1">
#### ✨ Filtering & Cleaning  
* Applied post‑processing to remove repetitive or near‑identical results  
* Optimized embeddings for **efficient vector search** in Pinecone
</div>
</div>

---

## ⚡ Optimization

Performance optimization ensured a smooth user experience:

1. **Latency Reduction:** Streamlined API calls, cutting end‑to‑end response from ~2 min ➜ **< 30 s**.  
2. **Prompt Engineering:** Tuned LLM prompts for contextual reranking.  
3. **Deduplication Logic:** Combined string and semantic similarity scores to prevent duplicates.

---

## 📈 Evaluation

- **Custom Dataset:** ~250 diverse queries for regression testing.  
- **Manual Review:** Visual inspection of top results with team feedback.  
- **Embedding Similarity:** CLIP‑based scores to evaluate alignment of images and queries.

---

## 🎯 Key Takeaways

This project delivered a full **end‑to‑end ML pipeline**—from data processing and semantic retrieval to latency optimization and live evaluation—strengthening my skills in **machine learning engineering, MLOps,** and **semantic search**.

<div class="skills-grid" markdown="1">
<div class="skill-item">🔍 Build hybrid search systems combining embeddings and LLMs</div>
<div class="skill-item">⚡ Optimize for accuracy *and* latency in production</div>
<div class="skill-item">☁️ Leverage vector databases & serverless architectures</div>
</div>

</div>

<style>
.blog-header {text-align:center;margin-bottom:2rem;padding:2rem 0;border-bottom:2px solid #e1e5e9;}
.blog-header .tag{background:#3498db;color:#fff;padding:0.2rem 0.5rem;border-radius:4px;font-size:0.8rem;margin-right:0.3rem;}
.blog-content{max-width:900px;margin:0 auto;line-height:1.7;font-size:1.05rem;}
.blog-content h2{color:#2c3e50;border-bottom:2px solid #3498db;padding-bottom:0.3rem;margin-top:2.5rem;font-size:1.8rem;}
.blog-content h3, .blog-content h4{color:#34495e;margin-top:2rem;}
.highlight-box{background:linear-gradient(135deg,#667eea 0%,#764ba2 100%);color:#fff;padding:1.2rem;border-radius:8px;margin:1.8rem 0;font-size:1.05rem;}
.objective-grid, .process-grid, .skills-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:1.3rem;margin:1.8rem 0;}
.objective-card, .process-card, .skill-item{background:#f8f9fa;padding:1.2rem;border-radius:8px;border-left:4px solid #3498db;}
.image-container{text-align:center;margin:2rem 0;}
.blog-image{width:100%;max-width:1100px;height:auto;border:1px solid #ddd;border-radius:8px;box-shadow:0 4px 8px rgba(0,0,0,0.1);}
.image-caption{font-style:italic;color:#666;margin-top:0.4rem;font-size:0.9rem;}
@media(max-width:768px){.blog-header{padding:1rem 0;}.blog-content h2{font-size:1.5rem;}.objective-grid,.process-grid,.skills-grid{grid-template-columns:1fr;}}
</style>
