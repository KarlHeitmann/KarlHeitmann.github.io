<!-- <h1 id="experience">Experience</h1> -->

<h3 class="cv-subtitle"><strong>Experience</strong></h3>

<div class="nodes">
  <ul class="first-level">
    {% for experience in site.data.experiences %}
      <li
        data-controller="experience"
      >
        <strong>{{ experience.name }}</strong>
        <small>{{ experience.role }}</small>
        <small>{{ experience.period }}</small>
        <small
        >{{ experience.place }}</small>
        <small
          data-action="click->experience#toggle"
          data-experience-target="togglebutton"
          style="cursor: pointer;">More ▼</small>
        <ul
          data-experience-target="detail"
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
      static targets = ["detail", "togglebutton"]

      toggle() {
        const className = 'visible'
        if (this.detailTarget.classList.contains(className)) {
          this.togglebuttonTarget.innerText = 'More ▼'
          this.detailTarget.classList.remove(className)
        } else {
          this.togglebuttonTarget.innerText = 'Less ▲'
          this.detailTarget.classList.add(className)
        }
      }
    })
  </script>

  <style>
    .second-level {
      /*
      height: 70px;
      height: 100%;
      */
      height: 0px;
      overflow-y: auto;
      /*transition: height 2s 2s;*/
      transition: height 1s;
    }

    .visible {
      /*
      height: 0%;
      height: 135px;
      */
      height: 205px;
    }

  </style>
</div>
