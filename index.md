---
title: "Home"
---

<section id="about" class="section">
  <div class="about-container">
    <img src="{{ '/assets/images/me.jpeg' | relative_url }}"
         alt="Michael Shoemaker"
         class="profile-pic">

    <div class="about-text">
      <h1>👋 Hi, I'm Michael Shoemaker</h1>
      <p>I build practical, production-like data engineering systems — orchestration, storage, transformations, serving, and observability — then explain the decisions behind them.</p>
      <p><strong>Core skills:</strong> Airflow · Spark · dbt · SQL Server · BigQuery · OpenSearch · Docker · GCP · CI/CD</p>
    </div>
  </div>
</section>

<!-- 🚀 Projects -->
<section id="projects" class="section">
  <div class="section-header">
    <h2>🚀 Projects</h2>
    <a class="view-all" href="https://github.com/{{ site.github_username }}" target="_blank" rel="noopener">All repos →</a>
  </div>

  <div class="carousel">
    <button class="scroll-btn left" data-target="#projects-track" aria-label="Scroll projects left">‹</button>
    <div id="projects-track" class="gallery horizontal-scroll">
      {% for item in site.data.projects %}
      <article class="card">
        <a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open project">
          <img src="{{ item.image | default: '/assets/images/placeholder_project.jpg' | relative_url }}"
               alt="{{ item.title | escape }} thumbnail"
               loading="lazy"
               {% if item.preview_gif %}data-preview="{{ item.preview_gif | relative_url }}"{% endif %}>
        </a>
        <div class="card-body">
          <h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
          <p class="card-text">{{ item.description }}</p>
          {% if item.stack %}<p class="card-tags">{{ item.stack }}</p>{% endif %}
          <div class="card-actions">
            {% if item.screenshot %}
              <a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>
            {% endif %}
            <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Open</a>
          </div>
        </div>
      </article>
      {% endfor %}
    </div>
    <button class="scroll-btn right" data-target="#projects-track" aria-label="Scroll projects right">›</button>
  </div>
</section>

<!-- 🎥 Videos -->
<section id="videos" class="section">
  <div class="section-header">
    <h2>🎥 Videos</h2>
    <a class="view-all" href="https://youtube.com/{{ site.youtube_channel }}" target="_blank" rel="noopener">Channel →</a>
  </div>

  <div class="carousel">
    <button class="scroll-btn left" data-target="#videos-track" aria-label="Scroll videos left">‹</button>
    <div id="videos-track" class="gallery horizontal-scroll">
      {% for item in site.data.videos %}
      <article class="card">
        <a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open video">
          <img src="{{ item.image | default: '/assets/images/placeholder_video.jpg' | relative_url }}"
               alt="{{ item.title | escape }} thumbnail"
               loading="lazy"
               {% if item.preview_gif %}data-preview="{{ item.preview_gif | relative_url }}"{% endif %}>
        </a>
        <div class="card-body">
          <h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
          {% if item.note %}<p class="card-text">{{ item.note }}</p>{% endif %}
          <div class="card-actions">
            {% if item.screenshot %}
              <a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>
            {% endif %}
            <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Watch</a>
          </div>
        </div>
      </article>
      {% endfor %}
    </div>
    <button class="scroll-btn right" data-target="#videos-track" aria-label="Scroll videos right">›</button>
  </div>
</section>

<!-- ✍️ Articles -->
<section id="articles" class="section">
  <div class="section-header">
    <h2>✍️ Articles</h2>
    <a class="view-all" href="https://medium.com/@{{ site.medium_username }}" target="_blank" rel="noopener">Medium →</a>
  </div>

  <div class="carousel">
    <button class="scroll-btn left" data-target="#articles-track" aria-label="Scroll articles left">‹</button>
    <div id="articles-track" class="gallery horizontal-scroll">
      {% for item in site.data.articles %}
      <article class="card">
        <a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open article">
          <img src="{{ item.image | default: '/assets/images/placeholder_article.jpg' | relative_url }}"
               alt="{{ item.title | escape }} thumbnail"
               loading="lazy"
               {% if item.preview_gif %}data-preview="{{ item.preview_gif | relative_url }}"{% endif %}>
        </a>
        <div class="card-body">
          <h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
          {% if item.subtitle %}<p class="card-text">{{ item.subtitle }}</p>{% endif %}
          <div class="card-actions">
            {% if item.screenshot %}
              <a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>
            {% endif %}
            <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Read</a>
          </div>
        </div>
      </article>
      {% endfor %}
    </div>
    <button class="scroll-btn right" data-target="#articles-track" aria-label="Scroll articles right">›</button>
  </div>
</section>

<script>
(function () {
  function setup(btn) {
    var targetSel = btn.getAttribute('data-target');
    var track = document.querySelector(targetSel);
    if (!track) return;

    var cards = track.querySelectorAll('.card');
    var leftBtn = track.parentElement.querySelector('.scroll-btn.left');
    var rightBtn = track.parentElement.querySelector('.scroll-btn.right');

    // Hide buttons entirely if <= 4 cards
    if (cards.length <= 4) {
      leftBtn.style.display = 'none';
      rightBtn.style.display = 'none';
      return;
    }

    var step = track.clientWidth * 0.9;

    btn.addEventListener('click', function () {
      track.scrollBy({ left: btn.classList.contains('left') ? -step : step, behavior: 'smooth' });
    });

    function update() {
      var max = track.scrollWidth - track.clientWidth - 1;
      var x = track.scrollLeft;
      if (leftBtn) leftBtn.disabled = x <= 0;
      if (rightBtn) rightBtn.disabled = x >= max;
    }

    track.addEventListener('scroll', update, { passive: true });
    window.addEventListener('resize', update);
    update();
  }

  document.querySelectorAll('.scroll-btn').forEach(setup);
})();
</script>
