<template>
  <header>
    <MainNavigation />
  </header>
  <MainHero />
  <AboutMe />
  <MySkills />
  <MyExperience />
  <MyProjects />
  <ContactMe />
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
  --primary-color: #374151;
  --grey: #dedede;
}
html {
  // background-color: var(--primary-color);
  //font-family: "Balsamiq Sans", "Manrope";
  // color: var(--grey);
}

body {
  margin: 0;
  padding: 40px 20px;
}
</style>
