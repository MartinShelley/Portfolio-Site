<template>
  <section id="my-career-timeline">
    <h2>My Experience</h2>
    <div class="centre-line">
      <div v-for="(value, key) in years" :key="key" class="years" :style="`left: ${(key * 20) + 10}%`">{{ value }}
      </div>
    </div>
    <div class=" jobs">
      <div v-for="( value, key ) in roles" :key=key class="job-wrapper" :job-role="value.company"
        :style="`left: ${(key * 20) + 10}%`">
        <h5 class="job-title">{{ value.jobTitle }} @</h5>
        <h5 class="job-title">{{ value.company }}</h5>
        <p class="job-duration">{{ value.duration }}</p>
        <!-- <p class="job-description" v-if="value.description">{{ value.description }}</p> -->
        <!-- <li v-for="( duty, index ) in value.duties" :key="index">{{ duty }}</li> -->
        <div class="skills">
          <li v-for="( skill, index ) in value.skills" :key="index">{{ skill }}</li>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      roles: [
        {
          company: 'Realtime DC',
          jobTitle: 'Sales and Application Specialist',
          duration: 'Aug 2014 - May 2016',
          skills: ['HTML', 'CSS', 'Wordpress']
          // duties: ['Using WordPress/CPanel to maintain UK website and to develop the USA website', 'Configure product setup & 1st/2nd line support for customers using Real-Link system'],
        },
        {
          company: 'Lynchpin Analytics',
          jobTitle: 'Data Engineer',
          duration: 'May 2016 - Oct 2018',
          skills: ['HTML', 'CSS', 'Javascript']
          // duties: ['Leading on the implementation of A/B tests for international clients', 'Led on other Analytics projects for big clients such as Ticketmaster & Hearst Magazines'],
        },
        {
          company: 'Racing Post',
          jobTitle: 'Implementation Specialist',
          duration: 'Dec 2018 - Oct 2021',
          skills: ['HTML', 'CSS', 'Javascript']
          // duties: ['Using Vanilla JS to add analytics tracking and embed 3rd party applications to Racing Post site', 'Spearheaded the integration of various third-party tools', 'Diagnosed issues and developed technical solutions (using Vanilla Javascript) for third-party tool integrations'],
          // tools: ['HTML', 'CSS', 'Javascript', 'Google Analytics', 'Google Tag Manager', 'Segment']
        },
        {
          company: 'The White Company',
          jobTitle: 'Front End Developer',
          duration: 'Nov 2021 - Aug 2023',
          skills: ['HTML', 'CSS', 'SASS', 'Javascript']
        },
        {
          company: 'I-Neda',
          jobTitle: 'Front End Developer',
          duration: 'Nov 2021 - Present',
          skills: ['HTML', 'CSS', 'SASS', 'Javascript', 'Angular', 'Typescript', 'Nativescript']
        }
      ],
      years: ['2014', '2016', '2018', '2021', '2023']
    }
  },
  methods: {

  }
}
</script>

<style lang="scss" scoped>
#my-career-timeline {
  position: relative;
  width: 100%;
  height: 750px;
  margin: 75px auto;

  h2 {
    text-align: center;
  }

  .centre-line {
    position: absolute;
    width: 100%;
    height: 3px;
    top: 50%;
    background-color: #000;
    border-radius: 5px;

    .years {
      position: absolute;
      transform: translateX(-50%);
      top: -15px;
      border: 1px solid black;
      border-radius: 100%;
      padding: 5px;
      background-color: #f4f4f4;

      &:nth-child(odd) {
        &::before {
          content: '';
          position: absolute;
          left: 50%;
          bottom: 100%;
          height: 125px;
          width: 1px;
          border-left: 1px solid #000;
        }
      }

      &:nth-child(even) {
        &:after {
          content: '';
          position: absolute;
          height: 125px;
          width: 1px;
          border-left: 1px solid #000;
          left: 50%;
          top: 100%;
        }
      }
    }
  }

  .jobs {
    // position: absolute;
    // height: 100%;
    // width: 100%;

    .job-wrapper {
      position: absolute;
      transform: translateX(-50%);
      text-align: center;
      width: 375px;
      height: 125px;
      padding: 5px;
      border: 1px solid black;
      border-radius: 10px;
      background-color: var(--orange);

      .job-title {
        font-size: 16px;
        margin: 0;
      }

      .job-duration {
        margin: 8px 0;
      }

      .job-duration,
      .skills {
        font-size: 14px;
      }

      .skills {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        column-gap: 10px;

        li {
          list-style-type: none;
        }
      }

      &:nth-child(odd) {
        top: 15%;
      }

      &:nth-child(even) {
        bottom: 15%;
      }
    }

    .job-wrapper[job-role="Realtime DC"] {
      visibility: visible !important;
    }
  }
}
</style>