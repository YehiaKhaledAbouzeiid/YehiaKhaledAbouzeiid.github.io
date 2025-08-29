---
title: Projects
---

# 🚀 Projects

{% for project in site.data.projects %}
- **[{{ project.title }}]({{ project.link }})** — {{ project.description }}
{% endfor %}
