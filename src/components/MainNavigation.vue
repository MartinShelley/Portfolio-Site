<template>
  <nav>
    <div class="logo">
      <img src="../assets/Dark_Logo.png" />
    </div>
    <ul class="main-navigation">
      <li>About Me</li>
      <li>Skills</li>
      <li>Experience</li>
      <li>Projects</li>
      <li>Contact</li>
    </ul>
  </nav>
</template>


<style lang="scss" scoped>
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;

  .main-navigation {
    display: flex;
    gap: 20px;

    li {
      // color: var(--grey);
      list-style: none;
    }
  }
}
</style>