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
import MainNavigation from "./components/MainNavigation.vue";
import MainHero from "./components/MainHero.vue";
import AboutMe from "./components/AboutMe.vue";
import MySkills from "./components/MySkills.vue";
import MyExperience from "./components/MyExperience.vue";
import MyProjects from "./components/MyProjects.vue";
import ContactMe from "./components/ContactMe.vue";

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
