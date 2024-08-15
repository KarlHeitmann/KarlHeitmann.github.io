<!-- # Education -->
<!-- <h1 id="education">Education</h1> -->

<h3 class="cv-subtitle"><strong>Education</strong></h3>

<div class="nodes">
  <!--<h3><i class="fa fa-briefcase"></i>Education</h3>-->
  <ul class="first-level">
    {% for education in site.data.educations %}
      <li>
        <strong>{{ education.name }}</strong>
        <small>{{ education.institution }}</small>
        <small>{{ education.place }} - {{ education.period }}</small>
        {% if education.extra %}
          <small>{{ education.extra }}</small>
        {% endif %}
      </li>
    {% endfor %}
  </ul>
</div>

