---
layout: default
title: Home
---

## About Me

I am an **Agentic AI & Software Engineer**, **Mechanical Engineer**, and **PhD Researcher in Radiative Heat Transfer** at [UFRN](https://ufrn.br).

My research and engineering efforts focus on the intersection of **computational physics** (radiative transfer, numerical solvers, simulation validation) and **agentic systems** (autonomous workflows, tool orchestration, MCP architectures, and persistent memory).

---

## Recent Posts

<ul>
  {% for post in site.posts %}
    <li>
      <span style="color: #666; font-size: 0.9em;">{{ post.date | date: "%B %d, %Y" }}</span> &mdash;
      <a href="{{ post.url | relative_url }}"><strong>{{ post.title }}</strong></a>
    </li>
  {% else %}
    <li><em>No posts yet. Stay tuned!</em></li>
  {% endfor %}
</ul>

---

## Key Areas & Projects

- **Scientific Computing & Solvers:** Numerical modeling, Monte Carlo methods, and transport phenomena.
- **Agentic AI & Tool Systems:** Autonomous agent harnesses, structured memory integration, and MCP servers.
