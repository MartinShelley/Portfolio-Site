<template>
  <header>
    <MainNavigation />
  </header>
  <main>
    <MainHero />
    <AboutMe />
    <MySkills />
    <MyExperience />
    <MyProjects />
  </main>
  <footer>
    <ContactMe />
  </footer>
</template>

<script>
import MainNavigation from "./components/Navigation/MainNavigation.vue";
import MainHero from "./components/MainHero/MainHero.vue";
import AboutMe from "./components/AboutMe/AboutMe.vue";
import MySkills from "./components/MySkills/MySkills.vue";
import MyExperience from "./components/Experience/MyExperience.vue";
import MyProjects from "./components/Experience/MyProjects.vue";
import ContactMe from "./components/Footer/ContactMe.vue";

export default {
  name: "App",
  components: {
    MainNavigation,
    MainHero,
    AboutMe,
    MySkills,
    MyExperience,
    MyProjects,
    ContactMe,
  },
  mounted() {
    window.onscroll = function () {
      if (this.oldScroll > this.scrollY) {
        document.querySelector("header").style.transform = "translateY(0%)";
      } else {
        document.querySelector("header").style.transform = "translateY(-100%)";
      }
      this.oldScroll = this.scrollY;
    };
  },
};
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
  box-shadow: 0px 0px 35px 1px rgb(0 0 0 / 10%);
  transition: all 0.25s cubic-bezier(0.645, 0.045, 0.355, 1);
  transform: translateY(0%);
}

body {
  margin: 0;
}

main {
  padding: 40px 100px;
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
}
</style>
