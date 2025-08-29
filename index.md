---
title: Home
---

<section id="about" class="section">
  <h1>👋 Hi, I'm Michael Shoemaker</h1>
  <p>I build practical, production-like data engineering systems — from real-time ingestion and orchestration to analytics and reporting. This page highlights a few flagship projects, short video walkthroughs, and articles. Everything here is open-source and reproducible.</p>
  <p><strong>Core skills:</strong> Airflow · Spark · dbt · SQL Server · BigQuery · OpenSearch/Elasticsearch · Docker · GCP · CI/CD</p>
</section>

<section id="projects" class="section">
  <h2>🚀 Projects</h2>
  <div class="grid">
    {% for project in site.data.projects %}
    <a class="card" href="{{ project.link }}" target="_blank" rel="noopener">
      <div class="card-body">
        <h3 class="card-title">{{ project.title }}</h3>
        <p class="card-text">{{ project.description }}</p>
        {% if project.stack %}
        <p class="card-tags">{{ project.stack }}</p>
        {% endif %}
      </div>
    </a>
    {% endfor %}
  </div>
</section>

<section id="videos" class="section">
  <h2>🎥 Videos</h2>
  <div class="grid">
    {% for video in site.data.videos %}
    <a class="card" href="{{ video.link }}" target="_blank" rel="noopener">
      <div class="card-body">
        <h3 class="card-title">{{ video.title }}</h3>
        {% if video.note %}<p class="card-text">{{ video.note }}</p>{% endif %}
      </div>
    </a>
    {% endfor %}
  </div>
</section>

<section id="articles" class="section">
  <h2>✍️ Articles</h2>
  <div class="grid">
    {% for article in site.data.articles %}
    <a class="card" href="{{ article.link }}" target="_blank" rel="noopener">
      <div class="card-body">
        <h3 class="card-title">{{ article.title }}</h3>
        {% if article.subtitle %}<p class="card-text">{{ article.subtitle }}</p>{% endif %}
      </div>
    </a>
    {% endfor %}
  </div>
</section>
