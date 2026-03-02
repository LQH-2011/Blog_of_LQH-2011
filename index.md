---
layout: default
title: Inicio
---
# Publicaciones Recientes
Aquí encontrarás mis investigaciones y reflexiones multidisciplinares. 
<!-- Bucle para listar los posts con paginación -->
<ul class="post-list">
  {% for post in paginator.posts %}
    <li>
      <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
      </h3>
      <p>{{ post.description }}</p>
    </li>
  {% endfor %}
</ul>
<!-- Controles de Navegación de Paginación -->
{% if paginator.total_pages > 1 %}
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path | relative_url }}">&laquo; Anterior</a>
  {% else %}
    <span>&laquo; Anterior</span>
  {% endif %}
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path | relative_url }}">Siguiente &raquo;</a>
  {% else %}
    <span>Siguiente &raquo;</span>
  {% endif %}
</div>
{% endif %}