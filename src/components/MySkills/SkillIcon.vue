<template>
  <figure>
    <img class="skill-icon" :src="require(`../../assets/skill-icons/${skill}-icon.svg`)" @mouseenter="toggleCaption"
      @mouseleave="toggleCaption" />
    <figcaption :skill="skill" v-show="hover">{{ formatCaption }}</figcaption>
  </figure>
</template>

<script>
export default {
  props: {
    skill: String,
  },
  data() {
    return {
      hover: false,
    };
  },
  methods: {
    toggleCaption() {
      this.hover = !this.hover;
    },
  },
  computed: {
    formatCaption() {
      return this.skill.replaceAll("-", " ");
    },
  },
};
</script>

<style lang="scss" scoped>
figure {
  margin: 0;
  display: flex;
  flex-direction: column;
  align-items: center;

  .skill-icon {
    height: 50px;
    width: 50px;
  }

  .skill-icon:hover {
    scale: 1.2;
  }

  figcaption {
    // display: none;
    margin-top: 10px;
    text-transform: capitalize;
  }
}

figcaption[skill="html"],
figcaption[skill="css"],
figcaption[skill="scss"],
figcaption[skill="sass"],
figcaption[skill="npm"] {
  text-transform: uppercase;
}
</style>