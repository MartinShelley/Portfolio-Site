<template>
  <Vue3Lottie :animationData="animation" :speed="0.75" :height="350" :width="350" :loop="false"
    @onComplete="toggleIsLoading" v-if="isLoading" />
  <div v-if="!isLoading" class="main-content">
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
import FooterCopyright from "./components/Footer/FooterCopyright.vue";

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
    FooterCopyright,
    Vue3Lottie
  },
  created() {
    window.addEventListener('scroll', this.scrollHandler);
  },
  data() {
    return {
      isLoading: true,
      animation
    }
  },
  methods: {
    toggleIsLoading() {
      this.isLoading = !this.isLoading;
      this.loadPage();
    },
    loadPage() {

    },
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
  --white: #f4f4f4;
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
  z-index: 10;
  background-color: white;
  transition: all 0.25s cubic-bezier(0.645, 0.045, 0.355, 1);
  transform: translateY(0%);

  &.mid-page {
    box-shadow: 0px 0px 35px 1px rgb(0 0 0 / 10%);
  }
}

body,
ul {
  margin: 0;
  padding: 0;
}

main {
  padding: 40px 200px 200px;
}

.main-content {
  animation-name: fade-in;
  animation-duration: 3s;
  animation-iteration-count: 1;
}

footer {
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

  &:hover {
    background-color: var(--white);
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

// .fade-enter-from {
//   opacity: 0;
// }

// .fade-enter-active {
//   transition: all 10s ease;
//   transition-delay: 5s;
// }

// .fade-enter-to {
//   opacity: 1;
// }</style>
