<template>
  <div :class="['header-nav-wrap', { 'header-scroll': isScroll }]">
    <nav
      class="header-nav"
      ref="headerNav"
      :class="{ 'header-scroll': isScroll }"
    >
      <h1><a href="#Home">Wang DoWon</a></h1>
      <ul>
        <li>
          <a href="#AboutMe"
            ><div class="underline"></div>
            About Me</a
          >
        </li>
        <li>
          <a href="#Skills"
            ><div class="underline"></div>
            Skills</a
          >
        </li>
        <li>
          <a href="#Link"
            ><div class="underline"></div>
            Link</a
          >
        </li>
        <li>
          <a href="#Projects"
            ><div class="underline"></div>
            Projects</a
          >
        </li>
      </ul>
    </nav>
  </div>

  <nav
    class="header-nav-small"
    ref="headerNavSmall"
    :class="{ 'header-scroll': isScroll || menu }"
  >
    <div>
      <h1><a href="#Home">Wang DoWon</a></h1>
      <button @click="openMenu"></button>
    </div>
    <transition name="slide">
      <ul v-if="menu">
        <li><a href="#AboutMe" @click="openMenu">About Me</a></li>
        <li><a href="#Skills" @click="openMenu">Skills</a></li>
        <li><a href="#Link" @click="openMenu">Link</a></li>
        <li><a href="#Projects" @click="openMenu">Projects</a></li>
      </ul>
    </transition>
  </nav>

  <div class="graybox" v-if="menu"></div>
</template>

<script>
export default {
  data() {
    return {
      menu: false,
      isScroll: false,
      currentView: "Home",
      ulWidth: 0,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.onScroll);
  },
  methods: {
    openMenu() {
      this.menu = !this.menu;
    },

    onScroll() {
      const currentScrollPosition =
        window.scrollY || document.documentElement.scrollTop;
      const headerHeight = 65;

      const homeHeight =
        document.querySelector(".home-box").offsetHeight - headerHeight;
      const aboutMeHeight =
        document.querySelector(".about-me").offsetHeight +
        homeHeight -
        headerHeight;
      const skillsHeight =
        document.querySelector(".skills-box").offsetHeight +
        aboutMeHeight -
        headerHeight;
      const linkHeight =
        document.querySelector(".link-box").offsetHeight +
        skillsHeight -
        headerHeight;

      if (currentScrollPosition > 0) {
        this.isScroll = true;
      } else {
        this.isScroll = false;
      }

      if (0 <= currentScrollPosition && currentScrollPosition < homeHeight) {
        this.currentView = "Home";
      } else if (
        homeHeight <= currentScrollPosition &&
        currentScrollPosition < aboutMeHeight
      ) {
        this.currentView = "About Me";
      } else if (
        aboutMeHeight <= currentScrollPosition &&
        currentScrollPosition < skillsHeight
      ) {
        this.currentView = "Skills";
      } else if (
        skillsHeight <= currentScrollPosition &&
        currentScrollPosition < linkHeight
      ) {
        this.currentView = "Link";
      }
    },
  },
};
</script>

<style scoped>
/* transition */

.slide-enter-active {
  -moz-transition-duration: 0.3s;
  -webkit-transition-duration: 0.3s;
  -o-transition-duration: 0.3s;
  transition-duration: 0.3s;
  -moz-transition-timing-function: ease-in;
  -webkit-transition-timing-function: ease-in;
  -o-transition-timing-function: ease-in;
  transition-timing-function: ease-in;
}

.slide-leave-active {
  -moz-transition-duration: 0.3s;
  -webkit-transition-duration: 0.3s;
  -o-transition-duration: 0.3s;
  transition-duration: 0.3s;
  -moz-transition-timing-function: cubic-bezier(0, 1, 0.5, 1);
  -webkit-transition-timing-function: cubic-bezier(0, 1, 0.5, 1);
  -o-transition-timing-function: cubic-bezier(0, 1, 0.5, 1);
  transition-timing-function: cubic-bezier(0, 1, 0.5, 1);
}

.slide-enter-from,
.slide-leave-to {
  overflow: hidden;
  max-height: 0;
}

.slide-enter-to,
.slide-leave-from {
  overflow: hidden;
  max-height: 220px;
}

/* header */
.header-nav-wrap,
.header-nav,
.header-nav-small {
  position: sticky;
  height: 64px;
  top: 0;
  left: 0;
  z-index: 100;
}

.header-scroll {
  background-color: white;
}

.header-nav {
  width: inherit;
  max-width: 1300px;
  display: none;
  justify-content: space-between;
  margin: 0 auto;
  font-size: 2rem;
  padding: 2rem;
}

.header-nav > h1 {
  flex: 1;
}

.header-nav > ul {
  display: flex;
  align-items: center;
  flex: 1;
}

.header-nav > ul > li {
  flex: 1;
  text-align: right;
}

.header-nav-small {
  width: inherit;
  max-width: 1300px;
  height: fit-content;
  margin: 0 auto;
  font-size: 2rem;
  padding: 2rem;
}

.header-nav-small > div {
  display: flex;
  justify-content: space-between;
}

.header-nav-small > ul {
  position: absolute;
  width: 100%;
  left: 0;
  top: 64px;
  background-color: #fff;
  border-top: solid lightgray 1px;
  box-shadow: 0px 5px 5px gray;
}

.header-nav-small > ul > li {
  margin: 2rem;
}

.header-nav-small > div > button {
  width: 24px;
  height: 24px;
  background-image: url("@/assets/img/round_menu_black_24dp.png");
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
}

a:link,
a:visited {
  color: black;
  text-decoration: none;
}

li > a {
  position: relative;
}

.underline {
  position: absolute;
  bottom: -1rem;
  left: 50%;
  width: 100%;
  height: 5px;
  background-color: gray;
  border-radius: 10rem;
  transition: width 0.3s ease 0s, left 0.3s ease 0s;
  width: 0;
}

a:hover > .underline {
  width: 100%;
  left: 0;
}

.header-nav > ul > li > a:hover {
  color: gray;
}

.spread-underline:hover:after {
  width: 100%;
  left: 0;
}

.graybox {
  position: fixed;
  top: 0;
  left: 0;
  background-color: gray;
  width: 100vw;
  height: 100vh;
  z-index: 1;
  opacity: 0.5;
}

@media (min-width: 719px) {
  .header-nav-small {
    display: none;
  }
  .header-nav {
    display: flex;
  }
}
</style>