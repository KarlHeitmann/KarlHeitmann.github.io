<!-- # Education -->
<!-- <h1 id="education">Education</h1> -->

<div class="nodes">
  <!--<h3><i class="fa fa-briefcase"></i>Education</h3>-->
  <ul class="first-level">
    {% for education in site.data.educations %}
      <li>
        <span>{{ education.name }}</span>
        <small>{{ education.institution }}</small>
        <small>{{ education.place }} - {{ education.period }}</small>
        {% if education.extra %}
          <small>{{ education.extra }}</small>
        {% endif %}
      </li>
    {% endfor %}
  </ul>
</div>

