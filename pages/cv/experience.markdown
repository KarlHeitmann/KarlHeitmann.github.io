<!-- <h1 id="experience">Experience</h1> -->

<h3 class="cv-subtitle"><strong>Experience</strong></h3>

<div class="nodes">
  <ul class="first-level">
    {% for experience in site.data.experiences %}
      <li
        data-controller="experience"
        data-action="click->experience#toggle"
        style="cursor: pointer;"
      >
        <strong>{{ experience.name }}</strong>
        <small>{{ experience.role }}</small>
        <small>{{ experience.period }}</small>
        <small
        >{{ experience.place }}</small>
        <ul
          hidden=""
          data-experience-target="main"
          class="second-level">
          {% for bullet_item in experience.bullet_list %}
            <li><small>{{ bullet_item }}</small></li>
          {% endfor %}
        </ul>
      </li>
    {% endfor %}
  </ul>

  <script type="module">
    window.Stimulus.register("experience", class extends window.Controller {
      static targets = ["main"]
      toggle() {
        console.log("Toggled!")
        this.mainTarget.hidden = !this.mainTarget.hidden
        // debugger
      }
    })
  </script>
</div>
