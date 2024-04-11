<template>
  <section id="my-career-timeline">
    <h2>My Timeline</h2>
    <div class="jobs">
      <div class="job-card" v-for="(value, key) in roles.slice().reverse()" :key="key"
        :style="{ 'top': `calc(${key * -5}px)` }">
        <h4 class="job-title">{{ value.jobTitle }} @ {{ value.company }}</h4>
        <p class="job-duration">{{ value.duration }}</p>
        <p class="job-description" v-if="value.description">{{ value.description }}</p>
        <ul class="skills">
          <li v-for="( skill, index ) in value.skills" :key="index">{{ skill }}</li>
        </ul>
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
          description: 'Using WordPress/CPanel to maintain UK website and to develop the USA website. Configure product setup & provide 1st/2nd line support for customers using Real-Link system.',
        },
        {
          company: 'Lynchpin Analytics',
          jobTitle: 'Data Engineer',
          duration: 'May 2016 - Oct 2018',
          skills: ['HTML', 'CSS', 'Javascript', 'jQuery'],
          description: 'Leading on the implementation of A/B tests for international clients. Led on other Analytics projects for big clients such as Ticketmaster & Hearst Magazines. Using Javascript to help implement and fix Analytics features on clients websites.'
        },
        {
          company: 'Racing Post',
          jobTitle: 'Implementation Specialist',
          duration: 'Dec 2018 - Oct 2021',
          skills: ['HTML', 'CSS', 'Javascript', 'jQuery', 'Segment'],
          // skills: ['HTML', 'CSS', 'Javascript', 'jQuery', 'Google Analytics', 'Google Tag Manager', 'Segment'],
          description: 'Using Vanilla Javascript to add analytics tracking and embed 3rd party applications to Racing Post site. Spearheaded the integration of various third-party tools through Racing Posts Customer Data Platform. Diagnosed issues and developed technical solutions (using Vanilla Javascript) for third-party tool integrations.'
        },
        {
          company: 'The White Company',
          jobTitle: 'Front End Developer',
          duration: 'Nov 2021 - Aug 2023',
          skills: ['HTML', 'CSS', 'SASS', 'Javascript', 'jQuery', 'Adobe Target', 'Adobe Launch'],
          description: 'Lead CRO developer at The White Company. Led on a comprehensive testing & personalisation roadmap where one test equated to an £1.8m annual incremental revenue benefit. Acted as main point of contact for technical & non-technical senior stakeholders. Worked closely with Product & Designers to implement their ideas onto the site & also ensured that crucial web features were rolled out onto the site gradually to allow for testing.'
        },
        {
          company: 'I-Neda',
          jobTitle: 'Front End Developer',
          duration: 'Sep 2023 - Present',
          skills: ['HTML', 'CSS', 'SASS', 'Javascript', 'Angular', 'Typescript', 'Nativescript'],
          description: 'Build and maintain Angular components across different client frontends. Led on a client project which introduced QR code scanning for a clients customers to enable them to scan their race tickets. Proactively addressed and resolved bugs, contributing to the overall stability and functionality of multiple client applications.'
        }
      ],
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
        flex-wrap: wrap;

        li {
          list-style: none;
          padding: 10px;
          background-color: var(--orange);
          color: var(--white);
          border-radius: 10px;
          font-weight: bold;
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

@media screen and (max-width: 768px) {
  #my-career-timeline {
    margin: 0 auto;

    .jobs {
      .job-card {
        &:nth-child(odd) {
          left: -15px
        }

        &:nth-child(even) {
          right: -15px;
        }
      }
    }
  }
}
</style>