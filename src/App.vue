<template>
  <header>
    <MainNavigation />
  </header>
  <main>
    <MainHero />
    <AboutMe />
    <MySkills />
    <MyTimeline />
    <MyProjects />
  </main>
  <footer>
    <ContactMe />
    <FooterCopyright />
  </footer>
</template>

<script>
import MainNavigation from "./components/Navigation/MainNavigation.vue";
import MainHero from "./components/MainHero/MainHero.vue";
import AboutMe from "./components/AboutMe/AboutMe.vue";
import MySkills from "./components/MySkills/MySkills.vue";
// import MyExperience from "./components/Experience/MyExperience.vue";
import MyTimeline from "./components/Experience/MyTimeline";
import MyProjects from "./components/Experience/MyProjects.vue";
import ContactMe from "./components/Footer/ContactMe.vue";
import FooterCopyright from "./components/Footer/FooterCopyright.vue";

export default {
  name: "App",
  components: {
    MainNavigation,
    MainHero,
    AboutMe,
    MySkills,
    MyTimeline,
    MyProjects,
    ContactMe,
    FooterCopyright,
  },
  created() {
    window.addEventListener('scroll', this.scrollHandler);
  },
  methods: {
    scrollHandler() {
      window.onscroll = function () {
        if (this.scrollY === 0) {
          document.querySelector('header').classList.remove('mid-page');
        }
        else if (this.oldScroll > this.scrollY) {
          document.querySelector('header').classList.add('mid-page');
          document.querySelector("header").style.transform = "translateY(0%)";
        }
        else {
          document.querySelector("header").style.transform = "translateY(-100%)";
        }
        this.oldScroll = this.scrollY;
      }
    },
    unmounted() {
      window.removeEventListener('scroll', this.scrollHandler);
    }
  }
}
</script>

<style lang="scss">
:root {
  --white: #fffbfb;
  --black: #000;
  --orange: #e77917;
}

html {
  font-family: "Nunito Sans", "Manrope", sans-serif;
}

header {
  position: fixed;
  top: 0;
  height: 100px;
  width: 100%;
  z-index: 1;
  background-color: white;
  transition: all 0.25s cubic-bezier(0.645, 0.045, 0.355, 1);
  transform: translateY(0%);

  &.mid-page {
    box-shadow: 0px 0px 35px 1px rgb(0 0 0 / 10%);
  }
}

body {
  margin: 0;
}

main {
  padding: 40px 200px;
}

footer {
  background-color: #f4f4f4;
  color: #1a1b1f;
  padding: 40px 200px 20px;
}

h1 {
  font-size: 65px;
}

h2 {
  font-size: 40px;
}

h3 {
  font-size: 30px;
}

button {
  background-color: var(--orange);
  opacity: 0.8;
  padding: 15px;
  font-weight: 600;
  width: 125px;
  border-radius: 4px;
  border: 1px solid #000;
  cursor: pointer;

  &:hover {
    background-color: var(--white);
  }
}
</style>
