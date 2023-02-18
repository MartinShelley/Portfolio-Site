<template>
  <nav>
    <div class="logo">
      <img src="../assets/ms-low-res.png" />
      <!-- <img src="https://via.placeholder.com/40" /> -->
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
  padding: 20px 100px;

  .logo {
    img {
      height: auto;
      width: 100px;
    }
  }

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