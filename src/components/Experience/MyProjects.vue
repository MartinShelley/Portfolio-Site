<template>
  <section id="my-projects">
    <h2>My Projects</h2>
    <Carousel :items-to-show="1" autoplay="2500" wrap-around="true" transition="500" pause-autoplay-on-hover="true">
      <Slide v-for="(project, index) in projects" :key="index" class="project">
        <img :src="getImgUrl(project.name)" />
        <div class="hover-card">
          <div class="card-content">
            <h4 class="project-title">{{ project.name }}</h4>
            <p class="tools">{{ project.madeWith }}</p>
            <div class="buttons">
              <a :href="project.gitHubLink" target="_blank">
                <button>View Code</button>
              </a>
              <a :href="project.liveEnvLink" target="_blank">
                <button>Live Demo</button>
              </a>
            </div>
          </div>
        </div>
      </Slide>
      <template #addons>
        <Pagination />
      </template>
    </Carousel>
    <!-- <div class="project"> -->

    <!-- </div> -->
    <!-- <div class="project"> -->

    <!-- </div> -->
    <!-- <div class="project"> -->

    <!-- </div> -->
    <!-- <div class="featured-projects">
      
      
      
    </div> -->
  </section>
</template>

<script>
import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Pagination } from 'vue3-carousel'
export default {
  data() {
    return {
      projects: {
        audiophileStore: {
          name: 'Audiophile Store Website',
          image: '../../assets/project-screenshots/audiophile-store-website.png',
          madeWith: 'Vue',
          gitHubLink: 'https://github.com/MartinShelley/Audiophile-Ecommerce-Site',
          liveEnvLink: 'https://audiophile-ecommerce-web-8fec7.web.app/'
        },
        entertainmentApp: {
          name: 'Entertainment Web App',
          image: '../../assets/project-screenshots/entertainment-web-app.png',
          madeWith: 'Angular',
          gitHubLink: 'https://github.com/MartinShelley/angular-entertainment-app',
          liveEnvLink: 'https://angular-entertainment-app.web.app/'
        },
        invoiceApp: {
          name: 'Invoicing App',
          image: '../../assets/project-screenshots/invoicing-app.png',
          madeWith: 'Vue',
          gitHubLink: 'https://github.com/MartinShelley/invoice-app',
          liveEnvLink: 'https://invoice-app-3517e.web.app/'
        }
      }
    }
  },
  methods: {
    getImgUrl(pic) {
      const picLabel = pic.replaceAll(' ', '-').toLowerCase();
      return require(`../../assets/project-screenshots/${picLabel}.png`);
    }
  },
  components: {
    Carousel,
    Slide,
    Pagination,
  }
}
</script>

<style lang="scss" scoped>
h2 {
  text-align: center;
}

// .featured-projects {
//   display: flex;
//   gap: 12px;

.project {
  display: flex;
  flex-direction: column;
  position: relative;
  // background: url('../../assets/project-screenshots/audiophile-website.png') center center/cover;
  // background-color: #cccccc;
  /* Used if the image is unavailable */
  // height: 500px;
  // width: 500px;
  // width: 800px;
  /* You must set a specified height */
  // background-position: center;
  // /* Center the image */
  // background-repeat: no-repeat;
  // /* Do not repeat the image */
  // background-size: cover;
  /* Resize the background image to cover the entire container */

  img {
    border-top-left-radius: 15px;
    border-top-right-radius: 15px;
    max-width: 900px;
    // height: 275px;
    // width: 800px;
  }

  .hover-card {
    position: absolute;
    opacity: 0;
    width: 100%;
    height: 100%;

    .card-content {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100%;

      .project-title {
        font-size: 20px;
        margin-bottom: 0;
      }

      .tools {
        padding: 10px;
        background-color: var(--orange);
        color: var(--white);
        border-radius: 10px;
        font-weight: bold;
      }

      .buttons {
        display: flex;
        gap: 10px;

        a {
          text-decoration: none;
          color: var(--black);
        }
      }
    }
  }

  &:hover {
    img {
      opacity: 0.1;
    }

    .hover-card {
      opacity: 1;
    }
  }
}

// }</style>