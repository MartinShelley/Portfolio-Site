<template>
  <section id="my-career-timeline">
    <h2>My Timeline</h2>
    <div class="jobs">
      <div class="job-card" v-for="(value, key) in roles" :key="key" :style="{ 'top': `calc(${key * -5}px)` }">
        <h4 class="job-title">{{ value.jobTitle }} @ {{ value.company }}</h4>
        <p class="job-duration">{{ value.duration }}</p>
        <p class="job-description" v-if="value.description">{{ value.description }}</p>
        <ul>
          <li v-for="(duty, index) in value.duties" :key="index">{{ duty }}</li>
        </ul>
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
          skills: ['HTML', 'CSS', 'Wordpress'],
          description: 'Fresh out of university, I landed my first role in technical customer support at Realtime DC where some of my duties included:',
          duties: ['Using WordPress/CPanel to maintain UK website and to develop the USA website', 'Configure product setup & 1st/2nd line support for customers using Real-Link system'],
        },
        {
          company: 'Lynchpin Analytics',
          jobTitle: 'Data Engineer',
          duration: 'May 2016 - Oct 2018',
          skills: ['HTML', 'CSS', 'Javascript'],
          // duties: ['Leading on the implementation of A/B tests for international clients', 'Led on other Analytics projects for big clients such as Ticketmaster & Hearst Magazines'],
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
        },
        {
          company: 'Racing Post',
          jobTitle: 'Implementation Specialist',
          duration: 'Dec 2018 - Oct 2021',
          skills: ['HTML', 'CSS', 'Javascript'],
          // duties: ['Using Vanilla JS to add analytics tracking and embed 3rd party applications to Racing Post site', 'Spearheaded the integration of various third-party tools', 'Diagnosed issues and developed technical solutions (using Vanilla Javascript) for third-party tool integrations'],
          // tools: ['HTML', 'CSS', 'Javascript', 'Google Analytics', 'Google Tag Manager', 'Segment']
          description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
        },
        {
          company: 'The White Company',
          jobTitle: 'Front End Developer',
          duration: 'Nov 2021 - Aug 2023',
          skills: ['HTML', 'CSS', 'SASS', 'Javascript'],
          description: 'During COVID, I decided I wanted to get into Web Development & I felt the best route for me to get into Web Development was to lean on my A/B testing/CRO experience. At The White Company, I was the lead CRO developer leading on a comprehensive testing & personalisation roadmap. I also:'
        },
        {
          company: 'I-Neda',
          jobTitle: 'Front End Developer',
          duration: 'Sep 2023 - Present',
          skills: ['HTML', 'CSS', 'SASS', 'Javascript', 'Angular', 'Typescript', 'Nativescript'],
          description: 'Continuing my Web Development journey, I wanted to work more with Front End frameworks and continue to develop as a Front End Developer and learn even more skills. At I-Neda I have:'
        }
      ],
      // years: ['2014', '2016', '2018', '2021', '2023']
    }
  },
  computed: {
    noOfJobs() {
      return this.roles.length;
    }
  }
}
</script>

<style lang="scss" scoped>
#my-career-timeline {
  position: relative;
  max-width: 800px;
  margin: 75px auto;

  h2 {
    text-align: center;
  }

  .jobs {
    .job-card {
      position: relative;
      border-top: 5px solid var(--orange);
      border-bottom: 5px solid var(--orange);
      padding: 20px;
      border-color: var(--orange);

      .skills {
        display: flex;
        gap: 20px;

        li {
          list-style: none;
          padding: 5px;
          background-color: var(--white);
          border: 2px solid var(--black);
          border-radius: 5px;
        }
      }


      &:nth-child(odd) {
        text-align: left;
        left: -30px;
        border-left: 5px solid var(--orange);
        border-radius: 30px 0 0 30px;

        .job-title::before {
          left: -15px;
          content: "";
          border-radius: 100%;
          border: 5px solid var(--orange);
          height: 15px;
          width: 15px;
          position: absolute;
          background-color: #fff;
        }
      }

      &:nth-child(even) {
        right: -30px;
        text-align: right;
        border-right: 5px solid var(--orange);
        border-radius: 0 30px 30px 0;

        .job-title::after {
          right: -15px;
          content: "";
          border-radius: 100%;
          border: 5px solid var(--orange);
          height: 15px;
          width: 15px;
          position: absolute;
          background-color: #fff;
        }

        .skills {
          justify-content: flex-end;
        }
      }

      &:first-child {
        top: 0;
        border-top: 0;
        border-top-left-radius: 0;
      }

      &:last-child {
        border-bottom: 0;
        border-bottom-left-radius: 0;
      }
    }
  }
}
</style>