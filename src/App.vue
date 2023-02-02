<template>
  <header>
    <MainNavigation />
    <MainHero />
    <AboutMe />
  </header>
</template>

<script>
import MainNavigation from "./components/MainNavigation.vue";
import MainHero from "./components/MainHero.vue";
import AboutMe from "./components/AboutMe.vue";

export default {
  name: "App",
  components: {
    MainNavigation,
    MainHero,
    AboutMe,
  },
};
</script>

<style lang="scss">
:root {
  --primary-color: #374151;
  --grey: #dedede;
}
html {
  background-color: var(--primary-color);
  //font-family: "Balsamiq Sans", "Manrope";
  color: var(--grey);
}

body {
  margin: 0;
  padding: 40px 20px;
}
</style>
