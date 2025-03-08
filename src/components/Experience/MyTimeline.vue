<template>
  <section id="my-career-timeline">
    <h2>My Timeline</h2>
    <div class="jobs">
      <div class="job-card" v-for="(value, key) in roles.slice().reverse()" :key="key"
        :style="{ 'transform': `translateY(calc(${key * -8}px))` }">
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
          description: 'Leading on the implementation of A/B tests for international clients. Led on other Analytics projects for big clients such as Ticketmaster & Hearst Magazines. Diagnose issues & developed solutions for 3rd party tool integrations (e.g. Google Analytics fix in response to Safari’s ITP deployment, ensuring the ability to target users on apps by using Braze).'
        },
        {
          company: 'Racing Post',
          jobTitle: 'Implementation Specialist',
          duration: 'Dec 2018 - Oct 2021',
          skills: ['HTML', 'CSS', 'Javascript', 'jQuery', 'Segment'],
          description: 'Responsible for the Google Tag Manager container for the Racing Post website, using JavaScript to add tracking and embed third party scripts. Spearheaded the integration of various third-party tools through Racing Posts Customer Data Platform. Diagnosed issues and developed technical solutions (using Javascript) for third-party tool integrations.'
        },
        {
          company: 'The White Company',
          jobTitle: 'Front End Developer',
          duration: 'Nov 2021 - Aug 2023',
          skills: ['HTML', 'CSS', 'SASS', 'Javascript', 'jQuery', 'Adobe Target', 'Adobe Launch'],
          description: 'Lead CRO developer at The White Company, responsible for delivering testing and personalisation initiatives from all areas of the company to optimise user experience & maximise revenue. Spearheaded a testing and personalization roadmap, delivering a standout test that resulted in a £1.8M annual incremental revenue benefit. Translated Figma and Sketch designs into pixel perfect responsive components for the UK, US & rest of world websites, ensuring consistency and high-quality delivery. Main point of contact for the team for both technical & non-technical senior stakeholders, including back-end developers, designers, product owners, product managers & directors.'
        },
        {
          company: 'I-Neda',
          jobTitle: 'Front End Developer',
          duration: 'Sep 2023 - Feb 2025',
          skills: ['HTML', 'CSS', 'SASS', 'Javascript', 'Angular', 'Typescript', 'Nativescript'],
          description: 'Involved in the implementation of a self-service betting terminal application for one of the largest racecourses in the country. Led a high-impact project for our largest client, successfully integrating QR code scanning functionality into their application, significantly enhancing usability and user experience. Oversaw the development of the account and registration journeys for a new Advance Deposit Wagering (ADW) platform, positioning the application to be pitched to new clients.'
        },
        {
          company: 'Bluebee',
          jobTitle: 'Senior Developer',
          duration: 'Feb 2025 - Present',
          skills: ['HTML', 'CSS', 'SASS', 'Javascript', 'Wordpress'],
          description: "Develop and maintain pixel-perfect websites and implement new features using WordPress' Gutenberg editor, HTML, CSS, and JavaScript. Assist clients in migrating DNS and mail servers to our hosting platform, ensuring a smooth transition. Deploy client websites to our hosting servers, following rigorous testing and pre-launch quality assurance checks. Collaborate with the marketing team to enhance client website SEO using Semrush, improving search engine visibility."
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
      border-top: 8px solid var(--orange);
      border-bottom: 8px solid var(--orange);
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
        border-left: 8px solid var(--orange);
        border-radius: 30px 0 0 30px;

        .job-title::before {
          left: -17px;
          content: "";
          border-radius: 100%;
          border: 8px solid var(--orange);
          height: 10px;
          width: 10px;
          position: absolute;
          background-color: #fff;
        }
      }

      &:nth-child(even) {
        right: -30px;
        text-align: right;
        border-right: 8px solid var(--orange);
        border-radius: 0 30px 30px 0;

        .job-title::after {
          right: -17px;
          content: "";
          border-radius: 100%;
          border: 8px solid var(--orange);
          height: 10px;
          width: 10px;
          position: absolute;
          background-color: #fff;
        }

        .skills {
          justify-content: flex-end;
        }
      }

      &:first-child {
        border-top: 0;
        border-top-left-radius: 0;
      }

      &:last-child {
        border-bottom: 0;
        border-bottom-left-radius: 0;
        border-bottom-right-radius: 0;
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