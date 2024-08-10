# Experience

<div class="nodes">
  <ul class="first-level">
    {% for experience in site.data.experiences %}
      <li>
        <span>{{ experience.name }}</span>
        <small>{{ experience.role }}</small>
        <small>{{ experience.period }}</small>
        <small>{{ experience.place }}</small>
        <ul>
          {% for bullet_item in experience.bullet_list %}
            <li><small>{{ bullet_item }}</small></li>
          {% endfor %}
        </ul>
      </li>
    {% endfor %}
  </ul>
</div>
