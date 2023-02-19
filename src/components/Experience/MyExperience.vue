<template>
  <section id="my-experience">
    <h2>My Experience</h2>
    <ul class="jobs">
      <li class="job-role">
        <div class="title">
          Front End Developer @ The White Company
          <span class="date-range">November 2021 - Present</span>
        </div>
        <ul class="role-responsibilities">
          <li>
            Lead Developer for the Personalisation of The White Company website
          </li>
          <li>
            Building high quality accessible functionality that impacted key
            stages of the users journey
          </li>
          <li>
            Taking Figma designs to build high quality, accurate content for the
            website
          </li>
        </ul>
      </li>
      <li class="job-role">
        <div class="title">
          Digital Data Analyst (Implementation Specialist) @ Spotlight Sports
          Group
          <span class="date-range">December 2018 - October 2021</span>
        </div>
        <ul class="role-responsibilities">
          <li>
            Using Vanilla JS & JQuery to enhance the website's analytics
            capabilites
          </li>
          <li>Led on integrations of numerous 3rd Party integrations</li>
        </ul>
      </li>
      <li class="job-role">
        <div class="title">
          Data Engineer @ Lynchpin Analytics
          <span class="date-range">May 2016 - October 2018</span>
        </div>
        <ul class="role-responsibilities">
          <li>
            Led on the implementation of several personalisation projects for
            clients such as Carphone Warehose & RBI (New Scientist Magazing &
            Farmers Weekly)
          </li>
          <li>
            Managing technical & non-technical stakeholder expectations across
            multiple different clients
          </li>
        </ul>
      </li>
      <li class="job-role">
        <div class="title">
          Sales & Application Specialist @ Realtime D.C
          <span class="date-range">August 2014 - May 2016 </span>
        </div>
        <ul class="role-responsibilities">
          <li>
            Maintaining the UK website & help to develop the US website using
            WordPress & CPanel
          </li>
          <li>
            Suggest and develop new possible solutions which would integrate
            with Real-link software.
          </li>
        </ul>
      </li>
    </ul>
  </section>
</template>

<style lang="scss" scoped>
h2 {
  text-align: center;
}
.jobs {
  display: grid;
  row-gap: 50px;
  list-style-type: none;

  .job-role {
    display: flex;
    justify-content: space-evenly;

    .title {
      display: flex;
      flex-direction: column;
      width: 350px;

      .date-range {
        font-size: 13px;
      }
    }
    .role-responsibilities {
      max-width: 500px;
    }
  }
}
</style>