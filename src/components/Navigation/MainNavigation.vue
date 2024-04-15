<template>
  <div class="header-wrapper">
    <div class="logo">
      <img src="../../assets/portfolio-logos/logo-no-background.svg" />
    </div>
    <nav id="desktop-nav" class="main-navigation">
      <ul>
        <li><a href="#about-me">About Me</a></li>
        <li><a href="#my-skills">Skills</a></li>
        <li><a href="#my-career-timeline">Experience</a></li>
        <li><a href="#my-projects">Projects</a></li>
        <li><a href="#contact-me">Contact</a></li>
      </ul>
    </nav>
    <div id="desktop-secondary-nav" class="secondary-navigation">
      <UserProfiles />
      <div class="open-to-work work-status">
        <div class="light"></div>
        <p>Open to work</p>
      </div>
    </div>
    <div id="hamburger-icon" @click="toggleHamburgerMenu" :class="showHamburgerMenu ? 'active' : ''">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </div>
  <div id="mobile-navigation">
    <div id="mobile-nav-background" :class="showHamburgerMenu ? 'show' : 'hide'"></div>
    <aside :class="showHamburgerMenu ? 'opened' : 'closed'">
      <div class="nav-wrapper">
        <nav class="main-navigation">
          <ul>
            <li @click="toggleHamburgerMenu"><a href="#about-me">About Me</a></li>
            <li @click="toggleHamburgerMenu"><a href="#my-skills">Skills</a></li>
            <li @click="toggleHamburgerMenu"><a href="#my-career-timeline">Experience</a></li>
            <li @click="toggleHamburgerMenu"><a href="#my-projects">Projects</a></li>
            <li @click="toggleHamburgerMenu"><a href="#contact-me">Contact</a></li>
          </ul>
        </nav>
        <div class="secondary-navigation">
          <UserProfiles />
          <div class="open-to-work work-status">
            <div class="light"></div>
            <p>Open to work</p>
          </div>
        </div>
      </div>
    </aside>
  </div>
</template>

<script>
import UserProfiles from "../Navigation/UserProfiles.vue";
export default {
  components: {
    UserProfiles,
  },
  data() {
    return {
      showHamburgerMenu: false
    }
  },
  methods: {
    toggleHamburgerMenu() {
      this.showHamburgerMenu = !this.showHamburgerMenu;
      if (this.showHamburgerMenu) {
        document.body.style.overflow = 'hidden';
      }
      else {
        document.body.style.overflow = 'unset';
      }
    }
  }
};
</script>


<style lang="scss" scoped>
.header-wrapper {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px 200px;

  .logo {
    img {
      height: auto;
      width: 100px;
    }
  }

  .secondary-navigation {
    display: flex;
    align-items: center;
    gap: 20px;
  }
}

.main-navigation ul {
  display: flex;
  gap: 20px;
  padding: 0;

  li {
    list-style: none;

    a {
      text-decoration: none;
      color: #000;
    }

    a:hover {
      color: var(--orange);
    }
  }
}

.work-status {
  display: flex;
  gap: 5px;
  align-items: center;

  .light {
    width: 10px;
    height: 10px;
    border-radius: 100%;
  }
}

.open-to-work {
  .light {
    animation: open-to-work 1s ease infinite;
  }
}

.unavailable-for-work {
  .light {
    animation: unavailable-for-work 1s ease infinite;
  }
}

#mobile-navigation {

  #mobile-nav-background {
    background-color: rgba(0, 0, 0, 0.5);
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    width: 100vw;
    height: 100vh;
    z-index: 1;
    transition: all ease 0.1s;

    &.show {
      opacity: 1;
      visibility: visible;
    }

    &.hide {
      opacity: 0;
      visibility: hidden;
    }
  }

  aside {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    height: 100dvh;
    width: 75vw;
    z-index: 2;
    background-color: #f4f4f4;
    transition: all ease-out 1s;


    &.opened {
      transform: translateX(0);
    }

    &.closed {
      transform: translateX(75vw);
    }

    .nav-wrapper {
      display: flex;
      flex-direction: column;
      height: 100%;
      justify-content: space-evenly;
      padding-left: 30px;

      .main-navigation ul {
        flex-direction: column;

        li {
          font-size: 32px;
        }
      }

      .work-status {
        p {
          font-size: 24px;
        }
      }
    }
  }
}

@media screen and (min-width: 1250px) {

  #hamburger-icon,
  #mobile-navigation {
    display: none
  }
}


@media screen and (max-width: 1250px) {

  #desktop-nav,
  #desktop-secondary-nav {
    display: none;
  }

  #hamburger-icon {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    z-index: 1000;
    width: 24px;
    height: 24px;

    span {
      display: block;
      height: 2px;
      width: 100%;
      background-color: #000;
      transition: all 0.5s cubic-bezier(.215, .61, .355, 1);
      transform-origin: left;
    }

    &.active {
      span:first-child {
        transform: rotate(45deg);
      }

      span:nth-child(2) {
        visibility: hidden;
        opacity: 0;
      }

      span:last-child {
        transform: rotate(-45deg);
      }
    }
  }

  #mobile-navigation {
    display: block;
  }

  .header-wrapper {
    padding: 20px 35px;

    .logo {
      height: 30px;
    }
  }
}

@keyframes open-to-work {
  0% {
    background-color: #eee;
    opacity: 0;
  }

  50% {
    background-color: #0FFF50;
    opacity: 1;
  }

  100% {
    background-color: #eee;
    opacity: 0;
  }
}

@keyframes unavailable-for-work {
  0% {
    background-color: #eee;
    opacity: 0;
  }

  50% {
    background-color: red;
    opacity: 1;
  }

  100% {
    background-color: #eee;
    opacity: 0;
  }
}
</style>