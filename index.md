---
layout: default
title: Home
---

<section id="projects" style="margin-top:48px;">
  <h2>🚀 Projects</h2>

  <div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:16px;margin-top:16px;">
    {% for p in site.data.projects %}
      <article style="background:#111827;border:1px solid #1f2937;border-radius:16px;overflow:hidden;">
        <div style="aspect-ratio:16/9;overflow:hidden;">
          <img src="{{ p.preview_gif | default: p.image }}" alt="{{ p.title }}" style="width:100%;height:100%;object-fit:cover;">
        </div>
        <div style="padding:16px;">
          <h3 style="margin:0 0 6px 0;">{{ p.title }}</h3>
          <p style="margin:0 0 8px 0;color:#cbd5e1;">{{ p.description }}</p>
          {% if p.stack %}
            <p style="margin:0 0 12px 0;font-size:0.9rem;color:#94a3b8;">{{ p.stack }}</p>
          {% endif %}
          <div>
            <a href="{{ p.link }}" target="_blank" style="text-decoration:none;background:#2563eb;color:white;padding:8px 12px;border-radius:10px;">Open</a>
          </div>
        </div>
      </article>
    {% endfor %}
  </div>
</section>


<div class="intro">
  <img src="/assets/images/avatar.png" alt="Yehia Khaled" style="width:120px;border-radius:50%;margin-right:16px;" />
  <div>
    <h1>Hello World! I'm <span class="highlight">Yehia Khaled</span></h1>

    <p style="font-size:18px; line-height:1.6; margin:16px 0; color:#e0e0e0;">
      <strong style="color:#00bcd4;">Database Administrator</strong> with 
      <strong style="color:#ff9800;">2+ years of Data experience</strong> and expertise in 
      <strong style="color:#8bc34a;">Microsoft Azure, SQL Server, Oracle, SSIS, SSMA, ETL, Tableau,</strong> 
      and <strong style="color:#f06292;">AI/ML tools</strong>.
    </p>

    <p style="font-size:18px; line-height:1.6; margin:16px 0; color:#e0e0e0;">
      Proven ability to manage and optimize critical banking databases with a focus on 
      <strong style="color:#4fc3f7;">high availability</strong>, 
      <strong style="color:#ba68c8;">disaster recovery</strong>, and 
      <strong style="color:#ff7043;">performance tuning</strong>.
    </p>

    <p style="font-size:18px; line-height:1.6; margin:16px 0; color:#e0e0e0;">
      Delivered measurable business value — reducing costs, improving system performance, and 
      impacting thousands of users across financial services and Data/AI projects.
    </p>

    <p><strong>Core skills:</strong> SQL Server · Oracle · PostgreSQL · MySQL · Airflow · dbt · Kafka · Azure · Power BI</p>
    <p>
      <a href="https://www.linkedin.com/in/yehiakhaledabouzeiid" target="_blank">LinkedIn</a> ·
      <a href="https://github.com/YehiaKhaledAbouzeiid" target="_blank">GitHub</a>
    </p>
  </div>
</div>
