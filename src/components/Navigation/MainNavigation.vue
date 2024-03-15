<template>
  <nav>
    <div class="logo">
      <img src="../../assets/portfolio-logos/logo-no-background.svg" />
    </div>
    <ul class="main-navigation">
      <li><a href="#about-me">About Me</a></li>
      <li><a href="#my-skills">Skills</a></li>
      <li><a href="#my-experience">Experience</a></li>
      <li><a href="#my-projects">Projects</a></li>
      <li><a href="#contact-me">Contact</a></li>
    </ul>
    <div class="other-nav">
      <UserProfiles />
      <div class="open-to-work work-status">
        <div class="light"></div>
        <p>Open to work</p>
      </div>
      <!-- <div class="unavailable-for-work work-status">
        <div class="light"></div>
        <p>Unavailable for work</p>
      </div> -->
    </div>
  </nav>
</template>

<script>
import UserProfiles from "../Navigation/UserProfiles.vue";
export default {
  components: {
    UserProfiles,
  },
};
</script>


<style lang="scss" scoped>
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 200px;

  .logo {
    img {
      height: auto;
      width: 100px;
    }
  }

  .main-navigation {
    display: flex;
    gap: 20px;
    padding: 0;

    li {
      list-style: none;

      a {
        text-decoration: none;
        color: #000;
      }

      a:hover {
        color: var(--orange);
      }
    }
  }

  .other-nav {
    display: flex;
    align-items: center;
    gap: 20px;

    .work-status {
      display: flex;
      gap: 5px;
      align-items: center;

      .light {
        width: 10px;
        height: 10px;
        border-radius: 100%;
      }

    }

    .open-to-work {
      .light {
        animation: open-to-work 1s ease infinite;
      }
    }

    .unavailable-for-work {
      .light {
        animation: unavailable-for-work 1s ease infinite;
      }
    }
  }

}

@keyframes open-to-work {
  0% {
    background-color: #eee;
    opacity: 0;
  }

  50% {
    background-color: #0FFF50;
    opacity: 1;
  }

  100% {
    background-color: #eee;
    opacity: 0;
  }
}

@keyframes unavailable-for-work {
  0% {
    background-color: #eee;
    opacity: 0;
  }

  50% {
    background-color: red;
    opacity: 1;
  }

  100% {
    background-color: #eee;
    opacity: 0;
  }
}
</style>