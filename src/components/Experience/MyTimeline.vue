<template>
  <section id="my-career-timeline">
    <h2>My Experience</h2>
    <div class="centre-line">
      <div v-for="(value, key) in years" :key="key" class="years" :style="`left: ${(key * 20) + 10}%`">{{ value }}
      </div>
    </div>
    <div class=" jobs">
      <div v-for="( value, key ) in roles" :key=key class="job-wrapper" :style="`left: ${(key * 20) + 10}%`">
        <h5 class="job-title">{{ value.jobTitle }} @ {{ value.company }}</h5>
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
          jobTitle: 'Digital Data Analyst (Implementation Specialist)',
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
  height: 500px;
  margin: 150px auto;


  h2 {
    text-align: center;
  }

  .centre-line {
    position: absolute;
    width: 100%;
    height: 3px;
    top: 50%;
    background-color: #000;

    .years {
      position: absolute;
      padding-top: 20px;
      transform: translateX(-50%);
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
      width: 450px;

      // h5 {
      //   width: 300px;
      // }

      &:nth-child(odd) {
        top: 20%;

        &::after {
          content: '';
          position: absolute;
          top: 100%;
          height: 15px;
          width: 1px;
          border-left: 1px solid #000;
        }
      }

      &:nth-child(even) {
        bottom: 20%;

        &::before {
          content: '';
          position: absolute;
          height: 15px;
          width: 1px;
          border-left: 1px solid #000;
        }
      }

      .skills {
        display: flex;

        li {
          list-style-type: none;
        }
      }
    }
  }
}
</style>