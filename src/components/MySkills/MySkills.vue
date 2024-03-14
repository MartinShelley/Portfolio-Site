<template>
  <section id="my-skills">
    <h2>Skills</h2>
    <div class="skills-grid">
      <SkillIcon :skill="item" v-for="item in skills" :key="item" />
    </div>
  </section>
</template>

<script>
import SkillIcon from "./SkillIcon.vue";
export default {
  data() {
    return {
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
        "node-js"
      ],
    };
  },
  components: {
    SkillIcon,
  },
};
</script>

<style lang="scss" scoped>
#my-skills {
  padding: 150px 0 0;

  h2 {
    text-align: center;
  }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(7, 150px);
    grid-template-rows: repeat(3, 125px);
    justify-items: center;
    justify-content: center;
  }
}
</style>