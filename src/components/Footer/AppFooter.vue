<template>
  <div>
    <UserProfiles />
    <p>&copy;2024 Martin Shelley.</p>
  </div>
</template>

<script>
import UserProfiles from "../Navigation/UserProfiles.vue";
export default {
  components: {
    UserProfiles,
  },
};
</script>

<style lang="scss" scoped>
div {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 25px 0 0;
}
</style>