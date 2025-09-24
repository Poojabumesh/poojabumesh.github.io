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
    url: "_posts/2025-07-30-ai-product-retrieval-fixed.md"
    btn_label: "Blog"
    btn_class: "btn--primary"
  - title: "Building a Three-in-One Tweet Intelligence Engine"
    excerpt: "Emotion classification, hashtag suggestions, popularity prediction in one pipeline."
    url: "https://github.com/Poojabumesh/Tweet_popularity_predictor"
    btn_label: "Project"
    btn_class: "btn--primary"
  - title: "A(I)YE Chef"
    excerpt: "Ingredient detection → RAG recipes, containerized on GCP."
    url: "https://github.com/Poojabumesh/A-I-YE-Chef"
    btn_label: "Project"
    btn_class: "btn--primary"
---

<!-- About block goes AFTER front matter, BEFORE the cards -->
<section class="about-blurb">
  <h2>About Me</h2>
  <p>
    I’m Pooja, a Machine Learning Engineer focused on retrieval-first AI systems:
    RAG pipelines, reranking, and production MLOps on AWS/GCP. I like taking ideas
    from notebook to reliable, observable services.
  </p>
  <ul>
    <li>RAG & Retrieval: embeddings, re-rankers, eval harnesses</li>
    <li>MLOps: MLflow, Docker/K8s, CI/CD, monitoring</li>
    <li>Cloud: AWS (Bedrock, S3), GCP (Vertex, Cloud Run)</li>
  </ul>
</section>

{% include feature_row %}
