---
title: "Building an AI-Powered Search with RAG, OpenAI, and Pinecone"
layout: post
date: 2025-07-30
categories: [LLMs, RAG, NLP]
tags: [OpenAI, Pinecone, AWS, HuggingFace, RAG, Lambda]
author: poojabumesh
excerpt: "During my internship as a Machine Learning Engineer at a fast-paced e-commerce startup, I worked on building a semantic search and recommendation system to improve product discovery in a large catalog."
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
---

<div class="blog-header">
  <h1 class="blog-title">{{ page.title }}</h1>
  <div class="blog-meta">
    <span class="blog-date">📅 {{ page.date | date: "%B %d, %Y" }}</span>
    <span class="blog-author">👨‍💻 {{ page.author }}</span>
    <span class="blog-tags">🏷️ 
      {% for tag in page.tags %}
        <span class="tag">{{ tag }}</span>
      {% endfor %}
    </span>
  </div>
</div>

<div class="blog-content">

## 🚀 Enhancing Product Search with AI: My Internship Experience

During my internship as a Machine Learning Engineer at a fast-paced e-commerce startup, I worked on building a semantic search and recommendation system to improve product discovery in a large catalog.

<div class="highlight-box">
💡 <strong>Key Challenge:</strong> Traditional keyword-based search often produced irrelevant results, making it difficult for users to quickly find what they needed.
</div>

---

## 🎯 Objective

The primary objective of my internship project was to **enhance product search and retrieval** using AI.

### What We Set Out to Accomplish:

<div class="objective-grid">
  <div class="objective-card">
    <h4>🧠 Understand User Intent</h4>
    <p>Go beyond simple keyword matching to understand what users really want</p>
  </div>
  
  <div class="objective-card">
    <h4>🔍 Semantic Retrieval</h4>
    <p>Retrieve semantically relevant products from a large catalog using embeddings</p>
  </div>
  
  <div class="objective-card">
    <h4>📊 Smart Reranking</h4>
    <p>Rerank results to present the most meaningful items first</p>
  </div>
</div>

By combining **machine learning, vector embeddings, and LLM-based reranking,** we aimed to create a system that significantly improved user search experience.

---

## 🏗️ Design

<div class="image-container">
  <img
    src="{{ '/assets/images/semantic_search.png' | relative_url }}"
    alt="System Architecture Diagram"
    class="blog-image"
  />
  <p class="image-caption"><em>System architecture showing the complete AI-powered search pipeline</em></p>
</div>

The system architecture was modular and consisted of the following components:

### 🎭 1. Intent Classification
<div class="component-section">
  <p><strong>Purpose:</strong> Categorized incoming queries to guide downstream processing</p>
  
  **Query Types:**
  - 🛍️ **Recommendation** → *"Suggest a fruity red wine"*
  - ℹ️ **Informational** → *"What is a Pinot Noir?"*
  - 💬 **Conversational** → *"I need a wine for dinner tonight"*
  
  <div class="tech-note">
  <strong>Impact:</strong> Guided the downstream retrieval and reranking logic for better results
  </div>
</div>

### 🔢 2. Vector-Based Retrieval
<div class="component-section">
  <p><strong>Core Technology:</strong> Semantic embeddings + vector similarity search</p>
  
  **Implementation Details:**
  - Embedded all product attributes into a **semantic vector space** using **sentence transformers**
  - Retrieved top candidate products using **cosine similarity** on **Pinecone vector database**
  
  <div class="tech-note">
  <strong>Why This Works:</strong> Captures meaning and context, not just keyword matches
  </div>
</div>

### 🎯 3. Reranking Layer
<div class="component-section">
  <p><strong>Refinement Stage:</strong> LLM-powered contextual reranking</p>
  
  **Process:**
  - Applied **LLM-powered reranking** (via Cohere Reranker) to refine the top results
  - Focused on **contextual relevance** to the query
  
  <div class="tech-note">
  <strong>Result:</strong> Dramatically improved relevance of final search results
  </div>
</div>

### 🧹 4. Duplicate Filtering
<div class="component-section">
  <p><strong>Quality Control:</strong> Ensuring clean, diverse results</p>
  
  **Methods:**
  - Used **Levenshtein distance** and semantic checks to remove near-duplicate products
  - Ensured cleaner, more diverse search results
  
  <div class="tech-note">
  <strong>Impact:</strong> Better user experience with varied, high-quality results
  </div>
</div>

### ☁️ 5. Deployment
<div class="component-section">
  <p><strong>Serverless Architecture:</strong> Scalable, cost-effective deployment</p>
  
  **Infrastructure:**
  - Deployed as a **serverless pipeline** using **AWS Lambda**, integrating Pinecone and third-party APIs for reranking
  - Designed for low-latency response in a real-time user interface
  
  <div class="tech-note">
  <strong>Benefits:</strong> Auto-scaling, reduced infrastructure costs, and seamless API integration
  </div>
</div>

---

## 📊 Data Processing

<div class="section-intro">
The data processing workflow was critical to enable semantic search:
</div>

<div class="process-grid">
  <div class="process-card">
    <h4>📦 Product Embeddings</h4>
    <ul>
      <li>Curated titles, descriptions, and attributes for thousands of products</li>
      <li>Generated <strong>dense embeddings</strong> with a pre-trained transformer</li>
    </ul>
  </div>

  <div class="process-card">
    <h4>🔍 Query Pre-processing</h4>
    <ul>
      <li>Normalized, tokenized, and embedded user queries in the same vector space</li>
      <li>Enabled direct <strong>semantic similarity</strong> comparisons between queries and products</li>
    </ul>
  </div>

  <div class="process-card">
    <h4>✨ Filtering & Cleaning</h4>
    <ul>
      <li>Applied post-processing to remove repetitive, low-quality, or near-identical results</li>
      <li>Optimized embeddings for <strong>efficient vector search</strong> in Pinecone</li>
    </ul>
  </div>
</div>

---

## ⚡ Optimization

<div class="section-intro">
Performance optimization was a key focus to ensure a smooth user experience:
</div>

<div class="optimization-section">
  <div class="optimization-item">
    <div class="optimization-header">
      <h4>🚀 1. Latency Reduction</h4>
      <div class="performance-badge">~2 minutes → <30 seconds</div>
    </div>
    <ul>
      <li>Streamlined API calls and restructured the pipeline</li>
      <li>Reduced <strong>end-to-end response time</strong> from <strong>~2 minutes to under 30 seconds</strong></li>
    </ul>
  </div>

  <div class="optimization-item">
    <div class="optimization-header">
      <h4>🎨 2. Prompt Engineering</h4>
    </div>
    <ul>
      <li>Tuned LLM prompts for <strong>contextual reranking</strong></li>
      <li>Improved semantic relevance and reduced ambiguous results</li>
    </ul>
  </div>

  <div class="optimization-item">
    <div class="optimization-header">
      <h4>🔄 3. Deduplication Logic</h4>
    </div>
    <ul>
      <li>Integrated <strong>string-based</strong> and <strong>semantic similarity scoring</strong></li>
      <li>Prevented duplicate or visually identical products in top recommendations</li>
    </ul>
  </div>
</div>

---

## 📈 Evaluation

<div class="section-intro">
To ensure the system was effective and robust:
</div>

<div class="evaluation-grid">
  <div class="evaluation-card">
    <h4>📋 Custom Evaluation Dataset</h4>
    <div class="metric-highlight">~250 diverse queries</div>
    <ul>
      <li>Created a test set of <strong>~250 diverse queries</strong> representing real user intent</li>
      <li>Used this for regression testing during iteration</li>
    </ul>
  </div>

  <div class="evaluation-card">
    <h4>👁️ Manual Review</h4>
    <div class="metric-highlight">Visual inspection</div>
    <ul>
      <li>Performed <strong>visual inspection</strong> of top results for subjective relevance</li>
      <li>Collected feedback from the team to improve reranking logic</li>
    </ul>
  </div>

  <div class="evaluation-card">
    <h4>🔍 Embedding Similarity Analysis</h4>
    <div class="metric-highlight">CLIP-based scoring</div>
    <ul>
      <li>Leveraged <strong>CLIP-based similarity scores</strong> to evaluate alignment between product images and query intent</li>
    </ul>
  </div>
</div>

---

## 🎯 Key Takeaways

<div class="takeaway-section">
  <div class="takeaway-header">
    <h3>🌟 Complete End-to-End ML Experience</h3>
    <p>This project was a complete <strong>end-to-end ML experience</strong> from <strong>data processing</strong> and <strong>semantic retrieval</strong> to <strong>latency optimization</strong> and <strong>evaluation in production</strong>.</p>
  </div>

  <div class="skills-learned">
    <h4>🧠 Skills I Developed:</h4>
    <div class="skills-grid">
      <div class="skill-item">
        <span class="skill-icon">🔍</span>
        <span>Build hybrid search systems combining embeddings and LLMs</span>
      </div>
      <div class="skill-item">
        <span class="skill-icon">⚡</span>
        <span>Optimize for both accuracy and latency in production ML pipelines</span>
      </div>
      <div class="skill-item">
        <span class="skill-icon">☁️</span>
        <span>Use vector databases and serverless architectures for scalable deployment</span>
      </div>
    </div>
  </div>

  <div class="final-note">
    This experience strengthened my skills in <strong>machine learning engineering, MLOps,</strong> and <strong>semantic search</strong>, while demonstrating how data science and domain knowledge can work together to improve user experience.
  </div>
</div>

</div>

<style>
.blog-header {
  text-align: center;
  margin-bottom: 2rem;
  padding: 2rem 0;
  border-bottom: 2px solid #e1e5e9;
}

.blog-title {
  font-size: 2.5rem;
  color: #2c3e50;
  margin-bottom: 1rem;
  font-weight: 700;
}

.blog-meta {
  display: flex;
  justify-content: center;
  gap: 2rem;
  flex-wrap: wrap;
  font-size: 0.9rem;
  color: #666;
}

.tag {
  background: #3498db;
  color: white;
  padding: 0.2rem 0.5rem;
  border-radius: 4px;
  font-size: 0.8rem;
  margin-right: 0.5rem;
}

.highlight-box {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 1.5rem;
  border-radius: 8px;
  margin: 2rem 0;
  font-size: 1.1rem;
}

.objective-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
}

.objective-card {
  background: #f8f9fa;
  padding: 1.5rem;
  border-radius: 8px;
  border-left: 4px solid #3498db;
  transition: transform 0.2s ease;
}

.objective-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.objective-card h4 {
  margin: 0 0 1rem 0;
  color: #2c3e50;
}

.component-section {
  background: #ffffff;
  border: 1px solid #e1e5e9;
  border-radius: 8px;
  padding: 1.5rem;
  margin: 1.5rem 0;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}

.tech-note {
  background: #e8f4fd;
  border-left: 4px solid #2196F3;
  padding: 1rem;
  margin: 1rem 0;
  border-radius: 0 4px 4px 0;
}

.image-container {
  text-align: center;
  margin: 2rem 0;
}

.blog-image {
  width: 100%;
  max-width: 1100px;
  height: auto;
  border: 1px solid #ddd;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}

.image-caption {
  font-style: italic;
  color: #666;
  margin-top: 0.5rem;
  font-size: 0.9rem;
}

.section-intro {
  font-size: 1.1rem;
  color: #555;
  margin-bottom: 2rem;
  font-style: italic;
}

.process-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
}

.process-card {
  background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
  padding: 1.5rem;
  border-radius: 8px;
  border-left: 4px solid #9b59b6;
}

.process-card h4 {
  color: #2c3e50;
  margin-bottom: 1rem;
}

.optimization-section {
  margin: 2rem 0;
}

.optimization-item {
  background: #fff;
  border: 1px solid #e1e5e9;
  border-radius: 8px;
  padding: 1.5rem;
  margin: 1rem 0;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}

.optimization-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
}

.performance-badge {
  background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-weight: bold;
  font-size: 0.9rem;
}

.evaluation-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
}

.evaluation-card {
  background: #fff;
  border: 1px solid #e1e5e9;
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
  transition: transform 0.2s ease;
}

.evaluation-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 16px rgba(0,0,0,0.1);
}

.metric-highlight {
  background: #ff6b6b;
  color: white;
  padding: 0.3rem 0.8rem;
  border-radius: 12px;
  font-size: 0.8rem;
  font-weight: bold;
  display: inline-block;
  margin-bottom: 1rem;
}

.takeaway-section {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 2rem;
  border-radius: 12px;
  margin: 2rem 0;
}

.takeaway-header h3 {
  color: white;
  margin-bottom: 1rem;
}

.skills-learned {
  margin: 2rem 0;
}

.skills-learned h4 {
  color: #f8f9fa;
  margin-bottom: 1rem;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1rem;
}

.skill-item {
  background: rgba(255,255,255,0.1);
  padding: 1rem;
  border-radius: 8px;
  display: flex;
  align-items: center;
  gap: 1rem;
}

.skill-icon {
  font-size: 1.5rem;
}

.final-note {
  background: rgba(255,255,255,0.1);
  padding: 1.5rem;
  border-radius: 8px;
  margin-top: 2rem;
  font-size: 1.1rem;
  line-height: 1.6;
}

.blog-content {
  max-width: 900px;
  margin: 0 auto;
  line-height: 1.7;
  font-size: 1.1rem;
}

.blog-content h2 {
  color: #2c3e50;
  border-bottom: 2px solid #3498db;
  padding-bottom: 0.5rem;
  margin-top: 3rem;
  font-size: 2rem;
}

.blog-content h3 {
  color: #34495e;
  margin-top: 2rem;
}

@media (max-width: 768px) {
  .blog-meta {
    flex-direction: column;
    gap: 0.5rem;
  }
  
  .objective-grid, .process-grid, .evaluation-grid, .skills-grid {
    grid-template-columns: 1fr;
  }
  
  .blog-title {
    font-size: 2rem;
  }
  
  .optimization-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.5rem;
  }
}
</style>
