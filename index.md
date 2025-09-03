---
title: "Home"
---

<!-- Inline carousel styles (scoped classes so they don't fight your grid) -->
<style>
  .carousel { position: relative; overflow: hidden; }
  .carousel-track {
    display: flex;
    gap: 1rem;
    flex-wrap: nowrap;            /* keep in one row */
    overflow-x: auto;
    scroll-behavior: smooth;
    padding-bottom: .25rem;
    -ms-overflow-style: none;     /* IE/Edge */
    scrollbar-width: none;        /* Firefox */
  }
  .carousel-track::-webkit-scrollbar { display: none; } /* WebKit */

  /* Make cards behave as slides */
  .carousel .card { flex: 0 0 300px; } /* adjust width to taste */

  /* Arrow buttons */
  .scroll-btn {
    position: absolute;
    top: 40%;
    transform: translateY(-50%);
    background: rgba(0,0,0,.45);
    color: #fff;
    border: 0;
    font-size: 2rem;
    line-height: 1;
    padding: .25rem .6rem;
    border-radius: .5rem;
    cursor: pointer;
    z-index: 2;
  }
  .scroll-btn.left { left: .25rem; }
  .scroll-btn.right { right: .25rem; }
  .scroll-btn[disabled] { opacity: .35; cursor: default; }
</style>

<section id="about" class="section">
  <div class="about-container">
    <img src="{{ '/assets/images/me.jpeg' | relative_url }}"
         alt="Michael Shoemaker"
         class="profile-pic">

    <div class="about-text">
      <h1>Hello World! I'm Michael Shoemaker</h1>
      <p>Senior Data Analyst | Teacher | Content Creator | .5x Programmer</p>
      <p>I build practical, production-like data engineering systems — orchestration, storage, transformations, serving, and observability — then explain the decisions behind them.</p>
      <p><strong>Core skills:</strong> Python · SQL · Linux · Airflow · Spark · BigQuery · Docker · GCP</p>
      
    <p class="social-links">
      <a href="https://www.linkedin.com/in/michaelshoemaker-1" target="_blank" aria-label="LinkedIn">
        <!-- LinkedIn SVG -->
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" viewBox="0 0 24 24">
          <path d="M4.98 3.5A2.5 2.5 0 1 1 5 8.5a2.5 2.5 0 0 1-.02-5zm.02 6.5H2v11h3V10zM8 10H5v11h3v-5.6c0-2.98 3.5-3.22 3.5 0V21H15v-6.52c0-5.38-5.83-5.18-7-2.54V10z"/>
        </svg>
      </a>

      <a href="https://www.youtube.com/@dataslinger6379" target="_blank" aria-label="YouTube">
        <!-- YouTube SVG -->
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" viewBox="0 0 24 24">
          <path d="M23.5 6.2a3 3 0 0 0-2.1-2.1C19.5 3.5 12 3.5 12 3.5s-7.5 0-9.4.6A3 3 0 0 0 .5 6.2C0 8.1 0 12 0 12s0 3.9.5 5.8a3 3 0 0 0 2.1 2.1c1.9.6 9.4.6 9.4.6s7.5 0 9.4-.6a3 3 0 0 0 2.1-2.1c.5-1.9.5-5.8.5-5.8s0-3.9-.5-5.8zM9.6 15.5v-7l6.2 3.5-6.2 3.5z"/>
        </svg>
      </a>
    </p>
    </div>
  </div>
</section>

<!-- ===================== Projects ===================== -->
<section id="projects" class="section">
  <div class="section-header">
    <h2>🚀 Projects</h2>
    <a class="view-all" href="https://github.com/{{ site.github_username }}" target="_blank" rel="noopener">All repos →</a>
  </div>

  {% assign projects_count = site.data.projects | size %}
  {% if projects_count > 4 %}
    <div class="carousel">
      <button class="scroll-btn left" data-target="#projects-track" aria-label="Scroll projects left">‹</button>
      <div id="projects-track" class="carousel-track" role="region" aria-label="Projects list">
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
              {% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
              <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Open</a>
            </div>
          </div>
        </article>
        {% endfor %}
      </div>
      <button class="scroll-btn right" data-target="#projects-track" aria-label="Scroll projects right">›</button>
    </div>
  {% else %}
    <div class="gallery">
      {% for item in site.data.projects %}
      <article class="card">
        <a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open project">
          <img src="{{ item.image | default: '/assets/images/placeholder_project.jpg' | relative_url }}"
               alt="{{ item.title | escape }} thumbnail" loading="lazy">
        </a>
        <div class="card-body">
          <h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
          <p class="card-text">{{ item.description }}</p>
          {% if item.stack %}<p class="card-tags">{{ item.stack }}</p>{% endif %}
          <div class="card-actions">
            {% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
            <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Open</a>
          </div>
        </div>
      </article>
      {% endfor %}
    </div>
  {% endif %}
</section>

<!-- ===================== Videos ===================== -->
<section id="videos" class="section">
  <div class="section-header">
    <h2>🎥 Videos</h2>
    <a class="view-all" href="https://youtube.com/{{ site.youtube_channel }}" target="_blank" rel="noopener">Channel →</a>
  </div>

  {% assign videos_count = site.data.videos | size %}
  {% if videos_count > 4 %}
    <div class="carousel">
      <button class="scroll-btn left" data-target="#videos-track" aria-label="Scroll videos left">‹</button>
      <div id="videos-track" class="carousel-track" role="region" aria-label="Videos list">
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
              {% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
              <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Watch</a>
            </div>
          </div>
        </article>
        {% endfor %}
      </div>
      <button class="scroll-btn right" data-target="#videos-track" aria-label="Scroll videos right">›</button>
    </div>
  {% else %}
    <div class="gallery">
      {% for item in site.data.videos %}
      <article class="card">
        <a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open video">
          <img src="{{ item.image | default: '/assets/images/placeholder_video.jpg' | relative_url }}"
               alt="{{ item.title | escape }} thumbnail" loading="lazy">
        </a>
        <div class="card-body">
          <h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
          {% if item.note %}<p class="card-text">{{ item.note }}</p>{% endif %}
          <div class="card-actions">
            {% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
            <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Watch</a>
          </div>
        </div>
      </article>
      {% endfor %}
    </div>
  {% endif %}
</section>

<!-- ===================== Articles ===================== -->
<section id="articles" class="section">
  <div class="section-header">
    <h2>✍️ Articles</h2>
    <a class="view-all" href="https://medium.com/@{{ site.medium_username }}" target="_blank" rel="noopener">Medium →</a>
  </div>

  {% assign articles_count = site.data.articles | size %}
  {% if articles_count > 4 %}
    <div class="carousel">
      <button class="scroll-btn left" data-target="#articles-track" aria-label="Scroll articles left">‹</button>
      <div id="articles-track" class="carousel-track" role="region" aria-label="Articles list">
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
              {% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
              <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Read</a>
            </div>
          </div>
        </article>
        {% endfor %}
      </div>
      <button class="scroll-btn right" data-target="#articles-track" aria-label="Scroll articles right">›</button>
    </div>
  {% else %}
    <div class="gallery">
      {% for item in site.data.articles %}
      <article class="card">
        <a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open article">
          <img src="{{ item.image | default: '/assets/images/placeholder_article.jpg' | relative_url }}"
               alt="{{ item.title | escape }} thumbnail" loading="lazy">
        </a>
        <div class="card-body">
          <h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
          {% if item.subtitle %}<p class="card-text">{{ item.subtitle }}</p>{% endif %}
          <div class="card-actions">
            {% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
            <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Read</a>
          </div>
        </div>
      </article>
      {% endfor %}
    </div>
  {% endif %}
</section>

<!-- Tiny helper script for arrow buttons -->
<script>
(function () {
  function init(btn) {
    var targetSel = btn.getAttribute('data-target');
    var track = document.querySelector(targetSel);
    if (!track) return;
    var step = Math.max(300, Math.floor(track.clientWidth * 0.9));

    btn.addEventListener('click', function () {
      track.scrollBy({ left: btn.classList.contains('left') ? -step : step, behavior: 'smooth' });
    });

    function update() {
      var max = track.scrollWidth - track.clientWidth - 1;
      var x = track.scrollLeft;
      var leftBtn = track.parentElement.querySelector('.scroll-btn.left');
      var rightBtn = track.parentElement.querySelector('.scroll-btn.right');
      if (leftBtn) leftBtn.disabled = x <= 0;
      if (rightBtn) rightBtn.disabled = x >= max;
    }
    track.addEventListener('scroll', update, { passive: true });
    window.addEventListener('resize', update);
    update();
  }
  document.querySelectorAll('.scroll-btn').forEach(init);
})();
</script>
