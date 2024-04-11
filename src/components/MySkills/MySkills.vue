<template>
  <section id="my-skills">
    <h2>Skills</h2>
    <div class="carousel">
      <div class="carousel-inner-wrapper">
        <SkillIcon :skill="item" v-for="item in skills" :key="item" @pauseAnimation="pauseCarousel($event)" />
      </div>
    </div>
  </section>
</template>

<script>
import SkillIcon from "./SkillIcon.vue";
export default {
  components: {
    SkillIcon,
  },
  data() {
    return {
      //included each skill twice to ensure carousel seems infinite
      skills: [
        "html",
        "css",
        "scss",
        "javascript",
        "jquery",
        "angular",
        "vue",
        "git",
        "github",
        "database",
        "npm",
        "google-analytics",
        "firebase",
        "google-tag-manager",
        "jira",
        "node-js",
        "html",
        "css",
        "scss",
        "javascript",
        "jquery",
        "angular",
        "vue",
        "git",
        "github",
        "database",
        "npm",
        "google-analytics",
        "firebase",
        "google-tag-manager",
        "jira",
        "node-js"
      ],
      carouselState: 'running'
    };
  },
  methods: {
    pauseCarousel(data) {
      return data ? this.carouselState = 'paused' : this.carouselState = 'running';
    }
  }
};
</script>

<style lang="scss" scoped>
#my-skills {
  h2 {
    text-align: center;
  }

  .carousel {
    max-width: 750px;
    position: relative;
    margin: 0 auto;
    overflow: hidden;

    &:before,
    &:after {
      content: "";
      height: 100px;
      position: absolute;
      width: 20px;
      z-index: 2;
    }

    &:before {
      background: linear-gradient(to right,
          rgba(255, 255, 255, 1) 0%,
          rgba(255, 255, 255, 0) 100%);
      top: 0;
      left: 0;
    }

    &:after {
      background: linear-gradient(to right,
          rgba(255, 255, 255, 0) 0%,
          rgba(255, 255, 255, 1) 100%);
      top: 0;
      right: 0;
    }

    .carousel-inner-wrapper {
      animation: skills-carousel 45s linear infinite;
      display: flex;
      justify-content: flex-start;
      gap: 20px;
      padding: 0 50px;
      animation-play-state: v-bind(carouselState);
    }
  }
}

@media screen and (max-width: 768px) {
  #my-skills {
    margin-top: 50px;

    h2 {
      margin-bottom: 15px;
    }

    .carousel {
      max-height: 125px;
    }
  }
}

@keyframes skills-carousel {
  0% {
    transform: translateX(0);
  }

  100% {
    transform: translateX(calc(-95px * 16))
  }
}
</style>