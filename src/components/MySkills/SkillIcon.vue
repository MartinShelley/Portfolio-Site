<template>
  <figure class="slide">
    <img class="skill-icon" :src="require(`../../assets/skill-icons/${skill}-icon.svg`)" :alt="skill" @mouseenter="toggleCaption"
      @mouseleave="toggleCaption" />
    <figcaption :skill="skill" :style="{ visibility: captionVisibility }">{{ formatCaption }}</figcaption>
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
      if (this.hover) {
        this.$emit('pauseAnimation', true);
      }
      else {
        this.$emit('pauseAnimation', false);
      }
    },
  },
  computed: {
    formatCaption() {
      return this.skill.replaceAll("-", " ");
    },
    captionVisibility() {
      return this.hover ? 'visible' : 'hidden';
    }
  },
};
</script>

<style lang="scss" scoped>
figure {
  margin: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px 0;

  .skill-icon {
    height: 60px;
    width: 75px;
  }

  .skill-icon:hover {
    scale: 1.1;
  }

  figcaption {
    margin-top: 10px;
    text-transform: capitalize;
    text-align: center;
    font-size: 14px;
    font-weight: bold;
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