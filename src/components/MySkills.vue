<template>
  <section id="my-skills">
    <h2>Skills</h2>
    <div class="skills-grid">
      <div class="first-column column">
        <figure>
          <img class="skill-icon" src="../assets/skill-icons/html-5.svg" />
          <figcaption>HTML</figcaption>
        </figure>
        <figure>
          <img class="skill-icon" src="../assets/skill-icons/jquery-icon.svg" />
          <figcaption>jQuery</figcaption>
        </figure>
        <figure>
          <img class="skill-icon" src="../assets/skill-icons/mysql-icon.svg" />
          <figcaption>SQL</figcaption>
        </figure>
        <figure>
          <img
            class="skill-icon"
            src="../assets/skill-icons/google-tag-manager.svg"
          />
          <figcaption>Google Tag Manager</figcaption>
        </figure>
      </div>
      <div class="second-column column">
        <figure>
          <img class="skill-icon" src="../assets/skill-icons/css-3.svg" />
          <figcaption>CSS</figcaption>
        </figure>
        <figure>
          <img class="skill-icon" src="../assets/skill-icons/vue.svg" />
          <figcaption>Vuejs</figcaption>
        </figure>
        <figure>
          <img class="skill-icon" src="../assets/skill-icons/npm-icon.svg" />
          <figcaption>npm</figcaption>
        </figure>
        <figure>
          <img class="skill-icon" src="../assets/skill-icons/jira.svg" />
          <figcaption>JIRA</figcaption>
        </figure>
      </div>
      <div class="third-column column">
        <figure>
          <img class="skill-icon" src="../assets/skill-icons/sass.svg" />
          <figcaption>Sass</figcaption>
        </figure>
        <figure>
          <img class="skill-icon" src="../assets/skill-icons/git-icon.svg" />
          <figcaption>Git</figcaption>
        </figure>
        <figure>
          <img
            class="skill-icon"
            src="../assets/skill-icons/google-analytics.svg"
          />
          <figcaption>Google Analytics</figcaption>
        </figure>
        <figure>
          <img
            class="skill-icon"
            src="../assets/skill-icons/GitHub/github-mark.png"
          />
          <figcaption>GitHub</figcaption>
        </figure>
      </div>
      <div class="fourth-column column">
        <figure>
          <img class="skill-icon" src="../assets/skill-icons/javascript.svg" />
          <figcaption>JavaScript</figcaption>
        </figure>
        <figure>
          <img
            class="skill-icon"
            src="../assets/skill-icons/cypress-icon.svg"
          />
          <figcaption>Cypress</figcaption>
        </figure>
        <figure>
          <img class="skill-icon" src="../assets/skill-icons/firebase.svg" />
          <figcaption>Firebase</figcaption>
        </figure>
        <figure>
          <img
            class="skill-icon"
            src="../assets/skill-icons/visual-studio-code.svg"
          />
          <figcaption>VS Code</figcaption>
        </figure>
      </div>
    </div>
  </section>
  <iframe
    width="100%"
    height="450"
    scrolling="no"
    frameborder="no"
    allow="autoplay"
    src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/playlists/1543745005&color=%23ff5500&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"
  ></iframe>
  <div
    style="
      font-size: 10px;
      color: #cccccc;
      line-break: anywhere;
      word-break: normal;
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
      font-family: Interstate, Lucida Grande, Lucida Sans Unicode, Lucida Sans,
        Garuda, Verdana, Tahoma, sans-serif;
      font-weight: 100;
    "
  >
    <a
      href="https://soundcloud.com/chillhopdotcom"
      title="Chillhop Music"
      target="_blank"
      style="color: #cccccc; text-decoration: none"
      >Chillhop Music</a
    >
    ·
    <a
      href="https://soundcloud.com/chillhopdotcom/sets/chillhop-yearmix-2022"
      title="Chillhop Yearmix 2022"
      target="_blank"
      style="color: #cccccc; text-decoration: none"
      >Chillhop Yearmix 2022</a
    >
  </div>
</template>

<style lang="scss" scoped>
.skills-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);

  .skill-icon {
    height: 50px;
    width: 50px;
  }
}
</style>