---
layout: default
title: Home
---

<div class="intro" style="display:flex; align-items:center; gap:20px; margin-bottom:20px;">
  <img src="/assets/images/me.png" alt="Yehia Khaled" style="width:110px; border-radius:50%;" />
  
  <div>
    <h1 style="font-size:26px; margin:0;">Hello Data Lovers! I'm <span class="highlight">Yehia Khaled</span></h1>

    <p style="font-size:16px; line-height:1.6; margin:12px 0; color:#e0e0e0;">
      <strong style="color:#fff;">Database Administrator</strong> with 
      <strong style="color:#fff;">2+ years of hands-on Data experience</strong>, specializing in 
      <strong style="color:#fff;">Microsoft SQL Server</strong> and 
      <strong style="color:#fff;">Oracle Database</strong>.
    </p>

    <p style="font-size:16px; line-height:1.6; margin:12px 0; color:#e0e0e0;">
      Proficient in managing, optimizing, and securing enterprise-grade databases with a focus on 
      <strong style="color:#fff;">high availability</strong>, 
      <strong style="color:#fff;">disaster recovery</strong>, and 
      <strong style="color:#fff;">performance tuning</strong>.
    </p>

    <p style="font-size:16px; line-height:1.6; margin:12px 0; color:#e0e0e0;">
      Additional knowledge across 
      <strong style="color:#fff;">MySQL, PostgreSQL, MongoDB, and Sybase ASE</strong>, with proven experience in 
      <strong style="color:#fff;">Tableau Server administration</strong>.
    </p>

    <p style="font-size:16px; line-height:1.6; margin:12px 0; color:#e0e0e0;">
      Delivered measurable business value, reducing costs, improving system performance, and enabling thousands of users across 
      <strong style="color:#fff;">financial services</strong> and 
      <strong style="color:#fff;">Data/AI projects</strong>.
    </p>

    <p><strong>Core skills:</strong> SQL Server · Oracle · MySQL · PostgreSQL · MongoDB · Sybase ASE · ADF · Fabric · Azure · Tableau Server · Power BI</p>

    <p>
      <a href="https://www.linkedin.com/in/yehia-khaled-abouzeid-005b8416a/" target="_blank">LinkedIn</a> ·
      <a href="https://github.com/YehiaKhaledAbouzeiid" target="_blank">GitHub</a>
    </p>
  </div>
</div>





<section id="projects" style="margin-top:48px;">
  <h2>🚀 Projects</h2>

  <div style="display:flex; gap:16px; margin-top:16px; overflow-x:auto; white-space:nowrap;">
    {% for p in site.data.projects %}
      <article style="flex:0 0 300px; background:#111827; border:1px solid #1f2937; border-radius:16px; overflow:hidden; display:inline-block;">
        <div style="aspect-ratio:16/9; overflow:hidden;">
          <img src="{{ p.preview_gif | default: p.image }}" alt="{{ p.title }}" style="width:100%; height:100%; object-fit:cover;">
        </div>
        <div style="padding:16px;">
          <h3 style="margin:0 0 6px 0;">{{ p.title }}</h3>
          <p style="margin:0 0 8px 0; color:#cbd5e1;">{{ p.description }}</p>
          {% if p.stack %}
            <p style="margin:0 0 12px 0; font-size:0.9rem; color:#94a3b8;">{{ p.stack }}</p>
          {% endif %}
          <div>
            <a href="{{ p.link }}" target="_blank" style="text-decoration:none; background:#2563eb; color:white; padding:8px 12px; border-radius:10px;">Open</a>
          </div>
        </div>
      </article>
    {% endfor %}
  </div>
</section>

