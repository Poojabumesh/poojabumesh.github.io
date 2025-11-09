---
layout: splash
title: "Machine Learning Engineer &#124; AI Engineer"
subtitle: "I build production-grade AI: retrieval pipelines, LLM orchestration, and reliable MLOps on AWS/GCP."
header:
  overlay_color: "#000"
  overlay_filter: 0.25
  overlay_image: /assets/images/gradient-hero.png
  actions:
    - label: "View Projects"
      url: /projects/
    - label: "Download Resume"
      url: /assets/POOJA_BARALU_UMESH.pdf
    - label: "Email Me"
      url: mailto:poojabumesh@gmail.com

# feature cards (all YAML stays in front matter)
feature_row:
  - title: "Building an AI-Powered Search with RAG, OpenAI, and Pinecone"
    excerpt: "OpenAI · Pinecone · Bedrock · Cohere reranker → measurable relevance gains."
    url: "/blog/ai-product-retrieval-fixed/"
    btn_label: "Blog"
    btn_class: "btn--primary"
  - title: "Building a Three-in-One Tweet Intelligence Engine"
    excerpt: "Emotion classification, hashtag suggestions, popularity prediction in one pipeline."
    url: "https://github.com/Poojabumesh/Tweet_popularity_predictor"
    btn_label: "Project"
    btn_class: "btn--primary"
  - title: "A(I)YE Chef"
    excerpt: "Built an ingredient detection pipeline using computer vision to identify food items, then match them to recipes. Containerized with Docker and deployed on GCP Cloud Run for scalable inference."
    url: "https://github.com/Poojabumesh/A-I-YE-Chef"
    btn_label: "Project"
    btn_class: "btn--primary"
---

<!-- About block goes AFTER front matter, BEFORE the cards -->
<section class="about-blurb">
  
  <h2>About Me</h2>
  <p>
    Hey, I'm Pooja 👋 — a Machine Learning Engineer specializing in <strong>retrieval-first AI systems</strong>.
    I build RAG pipelines, semantic search, and production ML infrastructure that actually scales.
  </p>
  <p>
    I love taking experimental ideas from Jupyter notebooks to <strong>reliable, observable services</strong> 
    running in production. My sweet spot is architecting end-to-end systems where retrieval quality, 
    latency, and reliability all matter.
  </p>
  <h3>What I Focus On</h3>
  <ul>
    <li>
      <strong>🔍 RAG & Retrieval:</strong> Semantic embeddings • Vector databases (Pinecone, FAISS) • 
      Cohere reranking • Custom eval frameworks • Retrieval optimization
    </li>
    <li>
      <strong>⚙️ MLOps & Infrastructure:</strong> MLflow experiment tracking • Docker/Kubernetes deployments • 
      CI/CD pipelines • Model monitoring & observability • FastAPI microservices
    </li>
    <li>
      <strong>☁️ Cloud & Scale:</strong> AWS (Bedrock, SageMaker, S3, EMR) • 
      GCP (Vertex AI, Cloud Run) • Distributed training • Production serving
    </li>
  </ul>
  <p>
    <em>Currently exploring: multi-modal retrieval, fine-tuning diffusion models, 
    and making LLMs work reliably in production.</em>
  </p>
</section>

{% include feature_row %}
