<template>
  <div class="footer-copyright">
    <UserProfiles />
    <p>&copy;2023 Martin Shelley.</p>
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
.footer-copyright {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 50px 0 0;
}
</style>