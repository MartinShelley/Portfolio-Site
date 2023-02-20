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
        "sass",
        "javascript",
        "JQuery",
        "VueJS",
        "git",
        "cypress",
        "MySQL",
        "npm",
        "google-analytics",
        "firebase",
        "google-tag-manager",
        "jira",
        "github",
        "visual-studio-code",
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
    grid-template-columns: repeat(4, 250px);
    grid-template-rows: repeat(4, 125px);
    justify-items: center;
    justify-content: center;
  }
}
</style>