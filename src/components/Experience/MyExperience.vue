<template>
  <section id="my-experience">
    <h2>My Experience</h2>
    <div class="job-titles">
      <a class="title" @click="openJobDescription($event, 'TWC')">
        <h4>The White Company</h4>
        <h5>Front End Developer</h5>
        <span class="date-range">November 2021 - Present</span>
      </a>
      <a class="title" @click="openJobDescription($event, 'SSG')">
        <h4>Spotlight Sports Group</h4>
        <h5>Digital Implementation Specialist</h5>
        <span class="date-range">December 2018 - October 2021</span>
      </a>
      <a class="title" @click="openJobDescription($event, 'Lynchpin')">
        <h4>Lynchpin Analytics</h4>
        <h5>Data Engineer</h5>
        <span class="date-range">May 2016 - October 2018</span>
      </a>
      <a class="title" @click="openJobDescription($event, 'RealtimeDC')">
        <h4>Realtime D.C</h4>
        <h5>Sales & Application Specialist</h5>
        <span class="date-range">August 2014 - May 2016 </span>
      </a>
      <div class="role-responsibilities">
        <div class="role-description" job-role="TWC">
          <span>
            Lead Developer for the Personalisation of The White Company website
          </span>
          <span>
            Building high quality accessible functionality that impacted key
            stages of the users journey
          </span>
          <span>
            Taking Figma designs to build high quality, accurate content for the
            website
          </span>
        </div>
        <div class="role-description" job-role="SSG">
          <span>
            Using Vanilla JS & JQuery to enhance the website's analytics
            capabilites
          </span>
          <span>Led on integrations of numerous 3rd Party integrations</span>
        </div>
        <div class="role-description" job-role="Lynchpin">
          <span>
            Led on the implementation of several personalisation projects for
            clients such as Carphone Warehose & RBI (New Scientist Magazing &
            Farmers Weekly)
          </span>
          <span>
            Managing technical & non-technical stakeholder expectations across
            multiple different clients
          </span>
        </div>
        <div class="role-description" job-role="RealtimeDC">
          <span>
            Maintaining the UK website & help to develop the US website using
            WordPress & CPanel
          </span>
          <span>
            Suggest and develop new possible solutions which would integrate
            with Real-link software.
          </span>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  methods: {
    openJobDescription(evt, jobRole) {
      console.log(evt);
      var i, x, tablinks;
      x = document.getElementsByClassName("role-description");
      for (i = 0; i < x.length; i++) {
        x[i].classList.remove("selected-job-role");
      }
      tablinks = document.getElementsByClassName("title");
      for (i = 0; i < x.length; i++) {
        tablinks[i].classList.remove("selected-title");
      }
      document
        .querySelector(`div[job-role="${jobRole}"]`)
        .classList.add("selected-job-role");
      evt.currentTarget.closest(".title").classList.add("selected-title");
    },
  },
};
</script>

<style lang="scss" scoped>
section {
  // padding: 100px 0;

  h2 {
    text-align: center;
  }
}

.job-titles {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: 0.5fr 1fr;
  row-gap: 25px;

  .title {
    border-bottom: 6px solid #ccc;
    cursor: pointer;
    display: flex;
    flex-direction: column;
    align-items: center;

    h4,
    h5 {
      margin: 0;
    }

    .date-range {
      font-size: 12px;
    }
  }

  .selected-title {
    border-bottom: 6px solid var(--orange);
  }

  .role-responsibilities {
    grid-column: 1 / 5;

    .role-description {
      display: none;
    }

    .selected-job-role {
      display: flex;
      flex-direction: column;
    }
  }
}
</style>