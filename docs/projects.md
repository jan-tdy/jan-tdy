---
layout: default
title: Jan-Tdy Projects
permalink: /projects
---

# My Projects

<div class="project-grid">
{% assign sorted_projects = site.projects | sort: "order" %}
{% for project in sorted_projects %}
    <a class="project-card" href="{{ project.url | relative_url }}">
        <div class="project-image-wrapper">
            {% if project.image %}
            <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" loading="lazy">
            {% endif %}
        </div>
        <div class="project-card-title">{{ project.title }}</div>
    </a>
{% endfor %}
</div>

<style>
    .project-grid {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 20px;
        margin-top: 30px;
    }

    .project-card {
        background: #161b22;
        border: 1px solid #30363d;
        border-radius: 10px;
        overflow: hidden;
        text-decoration: none;
        color: #c9d1d9;
        display: flex;
        flex-direction: column;
        box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.3);
        transition: transform 0.15s ease, border-color 0.15s ease;
    }

    .project-card:hover {
        transform: translateY(-2px);
        border-color: #58a6ff;
    }

    .project-image-wrapper {
        aspect-ratio: 4 / 3;
        background: #0d1117;
        overflow: hidden;
    }

    .project-image-wrapper img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        border-radius: 0;
        display: block;
    }

    .project-card-title {
        padding: 12px 14px;
        font-weight: 600;
        font-size: 1rem;
        text-align: center;
    }

    @media (max-width: 900px) {
        .project-grid { grid-template-columns: repeat(2, 1fr); }
    }

    @media (max-width: 520px) {
        .project-grid { grid-template-columns: 1fr; }
    }
</style>

---

For more details on any project, visit my [GitHub profile](https://github.com/jan-tdy).
