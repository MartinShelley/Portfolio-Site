<template>
  <Vue3Lottie :animationData="animation" :speed="0.75" :height="350" :width="350" :loop="false"
    @onComplete="toggleIsLoading" v-if="isLoading" class="starting-animation" />
  <div v-if="!isLoading" class="main-content">
    <header :class="[lastScrollPosition > 0 ? 'mid-page' : '', !showNavBar ? 'nav--hidden' : '']">
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
      <AppFooter />
    </footer>
  </div>
</template>

<script>
import MainNavigation from "./components/Navigation/MainNavigation.vue";
import MainHero from "./components/MainHero/MainHero.vue";
import AboutMe from "./components/AboutMe/AboutMe.vue";
import MySkills from "./components/MySkills/MySkills.vue";
import MyTimeline from "./components/Experience/MyTimeline";
import MyProjects from "./components/Experience/MyProjects.vue";
import ContactMe from "./components/Footer/ContactMe.vue";
import AppFooter from "./components/Footer/AppFooter.vue";

import { Vue3Lottie } from 'vue3-lottie'
import animation from "./assets/Animation.json";

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
    AppFooter,
    Vue3Lottie
  },
  data() {
    return {
      isLoading: true,
      showNavBar: true,
      lastScrollPosition: 0,
      animation
    }
  },
  mounted() {
    window.addEventListener('scroll', this.scrollHandler);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.scrollHandler);
  },
  methods: {
    toggleIsLoading() {
      this.isLoading = !this.isLoading;
    },
    scrollHandler() {
      const currentScrolledPosition = window.scrollY || document.documentElement.scrollTop;

      if (currentScrolledPosition <= 0) {
        this.lastScrollPosition = 0;
        return;
      }

      if (Math.abs(currentScrolledPosition - this.lastScrollPosition) < 50) {
        return
      }

      this.showNavBar = currentScrolledPosition < this.lastScrollPosition;
      this.lastScrollPosition = currentScrolledPosition;
    },
    unmounted() {
      window.removeEventListener('scroll', this.scrollHandler);
    }
  }
}
</script>

<style lang="scss">
:root {
  --white: #f4f4f4;
  --black: #000;
  --orange: #e77917;
}

html,
body {
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
}

html {
  box-sizing: border-box;
  font-family: "Nunito Sans", "Manrope", sans-serif;
  scroll-behavior: smooth;
}

header {
  position: fixed;
  top: 0;
  height: 100px;
  width: 100%;
  z-index: 10;
  background-color: white;
  transition: all 0.25s cubic-bezier(0.645, 0.045, 0.355, 1);
  transform: translateY(0%);
  box-shadow: none;

  &.mid-page {
    box-shadow: 0px 0px 35px 1px rgb(0 0 0 / 10%);
  }

  &.nav--hidden {
    transform: translateY(-100%);
    box-shadow: none;
  }
}

body,
ul {
  margin: 0;
  padding: 0;
}

main {
  padding: 0 200px 200px;
}

section {
  scroll-margin-top: 100px;
}

.main-content {
  animation-name: fade-in;
  animation-duration: 3s;
  animation-iteration-count: 1;
}

footer {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: var(--white);
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

.button {
  background-color: var(--orange);
  opacity: 0.8;
  padding: 15px;
  font-weight: 600;
  width: 125px;
  border-radius: 4px;
  border: 1px solid #000;
  cursor: pointer;
  color: #000;

  &:hover {
    background-color: var(--white);
  }
}

@media screen and (max-width: 1250px) {
  header {
    height: unset;
  }
}

@media screen and (max-width: 1000px) and (min-width: 768px) {

  main {
    padding: 40px 100px 150px;
  }

  footer {
    padding: 40px 100px;
  }
}

@media screen and (max-width: 767px) {

  main {
    padding: 20px 35px 100px;
  }

  footer {
    padding: 20px 35px;
  }

  h1 {
    font-size: 36px;
  }

  h2 {
    font-size: 30px;
  }

  h3 {
    font-size: 20px;
  }

  .starting-animation {
    width: 300px;
  }
}

@keyframes fade-in {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
  }

}
</style>