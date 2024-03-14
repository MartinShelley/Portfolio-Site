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
    <UserProfiles />
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
}
</style>