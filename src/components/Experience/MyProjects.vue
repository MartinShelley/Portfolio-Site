<template>
  <section id="my-projects">
    <h2>My Projects</h2>
    <div class="featured-projects">
      <div class="project">
        <img src="../../assets/project-screenshots/audiophile-website.png" />
        <div class="hover-card">
          <div class="card-content">
            <h4 class="project-title">Audiophile Store Website</h4>
            <p class="tools">Vue</p>
            <div class="buttons">
              <a href="https://github.com/MartinShelley/Audiophile-Ecommerce-Site">
                <button>View Code</button>
              </a>
              <a href="https://audiophile-ecommerce-web-8fec7.web.app/">
                <button>Live Demo</button>
              </a>
            </div>
          </div>
        </div>
      </div>
      <div class="project">
        <img src="../../assets/project-screenshots/entertainment-web-app.png" />
        <div class="hover-card">
          <div class="card-content">
            <h4 class="project-title">Entertainment Web App</h4>
            <p class="tools">Angular</p>
            <div class="buttons">
              <a href="https://github.com/MartinShelley/angular-entertainment-app">
                <button>View Code</button>
              </a>
              <a href="https://angular-entertainment-app.web.app/">
                <button>Live Demo</button>
              </a>
            </div>
          </div>
        </div>
      </div>
      <div class="project">
        <img src="../../assets/project-screenshots/invoicing-app.png" />
        <div class="hover-card">
          <div class="card-content">
            <h4 class="project-title">Invoicing App</h4>
            <p class="tools">Vue</p>
            <div class="buttons">
              <a href="https://github.com/MartinShelley/invoice-app">
                <button>View Code</button>
              </a>
              <a href="https://invoice-app-3517e.web.app/">
                <button>Live Demo</button>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
h2 {
  text-align: center;
}

.featured-projects {
  display: flex;
  gap: 12px;

  .project {
    display: flex;
    flex-direction: column;
    position: relative;

    img {
      border-top-left-radius: 15px;
      border-top-right-radius: 15px;
      height: 275px;
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
}
</style>