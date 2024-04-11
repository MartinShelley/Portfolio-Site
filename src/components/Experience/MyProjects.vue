<template>
  <section id="my-projects">
    <h2>My Projects</h2>
    <Carousel :items-to-show="1" :autoplay=3000 :wrap-around=true :transition=1000 :pause-autoplay-on-hover=true>
      <Slide v-for="(project, index) in projects" :key="index" class="project">
        <img :src="getImgUrl(project.name)" v-if="project.gitHubLink" />
        <div class="hover-card" v-if="project.gitHubLink">
          <div class="card-content">
            <h4 class="project-title">{{ project.name }}</h4>
            <p class="tools">{{ project.madeWith }}</p>
            <div class="buttons">
              <a :href="project.gitHubLink" target="_blank">
                <button class="button">View Code</button>
              </a>
              <a :href="project.liveEnvLink" target="_blank">
                <button class="button">Live Demo</button>
              </a>
            </div>
          </div>
        </div>
        <div class="coming-soon" v-else>
          <h3>More Coming Soon...</h3>
        </div>
      </Slide>
      <template #addons>
        <Pagination />
      </template>
    </Carousel>
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
        },
        comingSoon: {
          name: 'Coming Soon'
        }
      }
    }
  },
  methods: {
    getImgUrl(pic) {
      const picLabel = pic.replaceAll(' ', '-').toLowerCase();
      return require(`../../assets/project-screenshots/${picLabel}.png`);
    },
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

#my-projects {
  max-width: 800px;
  margin: 0 auto;
}

.project {
  display: flex;
  flex-direction: column;
  position: relative;

  img {
    border-top-left-radius: 15px;
    border-top-right-radius: 15px;
    width: 100%;
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

  .coming-soon {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100%;
    width: 100%;
    background-color: #f4f4f4;
    border-top-left-radius: 15px;
    border-top-right-radius: 15px;
  }

  &:hover {
    img {
      opacity: 0.1;
    }

    .hover-card {
      opacity: 1;
    }
  }

  // &:active {
  //   img {
  //     opacity: 0.1;
  //   }

  //   .hover-card {
  //     opacity: 1;
  //   }
  // }

}

ol.carousel__pagination {
  padding-left: 0 !important;
}

@media screen and (max-width: 768px) {
  #my-projects {
    margin-top: 50px;
  }

  .project {
    .hover-card {
      .card-content {
        .project-title {
          font-size: 16px;
          margin: 0;
        }

        .tools {
          padding: 8px;
          font-size: 12px;
          margin: 8px 0;
        }
      }
    }
  }
}

button {
  padding: 8px;
  width: 100px;
  font-size: 12px;
}
</style>