<template>
  <div class="header-nav-wrap">
    <nav class="header-nav">
      <h1><a href="#">Wang DoWon</a></h1>
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

  <nav class="header-nav-small">
    <div>
      <div class="header-nav-small-titlebox">
        <h1><a href="#Home" @click="menu = false">WDW's</a></h1>
        <span>{{ currentView }}</span>
      </div>

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
      currentView: "Portfolio",
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
      const homeScrollTop = document.querySelector("#Home").offsetTop;
      const aboutMeScrollTop = document.querySelector("#AboutMe").offsetTop;
      const skillsScrollTop = document.querySelector("#Skills").offsetTop;
      const linkScrollTop = document.querySelector("#Link").offsetTop;
      const projectsScrollTop = document.querySelector("#Projects").offsetTop;

      if (currentScrollPosition >= aboutMeScrollTop) {
        this.isScroll = true;
      } else {
        this.isScroll = false;
      }

      if (
        homeScrollTop <= currentScrollPosition &&
        currentScrollPosition < aboutMeScrollTop
      ) {
        this.currentView = "Portfolio";
      } else if (
        aboutMeScrollTop <= currentScrollPosition &&
        currentScrollPosition < skillsScrollTop
      ) {
        this.currentView = "About Me";
      } else if (
        skillsScrollTop <= currentScrollPosition &&
        currentScrollPosition < linkScrollTop
      ) {
        this.currentView = "Skills";
      } else if (
        linkScrollTop <= currentScrollPosition &&
        currentScrollPosition < projectsScrollTop
      ) {
        this.currentView = "Link";
      } else if (projectsScrollTop <= currentScrollPosition) {
        this.currentView = "Projects";
      }
    },
  },
};
</script>

<style scoped>
/* header */
h1 {
  font-weight: bold;
}

.header-nav-wrap,
.header-nav,
.header-nav-small {
  position: sticky;
  top: 0;
  left: 0;
  z-index: 100;
  background-color: white;
  font-size: 1rem;
}

.header-nav-wrap {
  display: none;
  border-bottom: solid lightgray 1px;
}

.header-nav {
  width: inherit;
  max-width: 1300px;
  display: none;
  height: 64px;
  justify-content: space-between;
  align-items: center;
  margin: 0 auto;
  font-size: 1.2em;
}

.header-nav > h1 {
  flex: 1;
  margin-left: 1rem;
}

.header-nav > ul {
  display: flex;
  align-items: center;
  flex: 1;
  margin-right: 1rem;
}

.header-nav > ul > li {
  flex: 1;
  text-align: right;
  font-weight: bolder;
}

.header-nav-small {
  width: inherit;
  max-width: 1300px;
  height: 64px;
  margin: 0 auto;
  font-size: 1.2em;
  border-bottom: solid lightgray 1px;
}

.header-nav-small > div {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 0 1rem;
  height: inherit;
}

.header-nav-small-titlebox {
  display: flex;
  align-items: center;
}

.header-nav-small-titlebox > span {
  font-size: 1em;
  margin-left: 0.5em;
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
  margin: 3rem 2rem;
}

.header-nav-small > div > button {
  width: 24px;
  height: 24px;
  background-image: url("@/assets/img/round_menu_black_24dp.png");
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
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

@media (min-width: 800px) {
  .header-nav-small {
    display: none;
  }
  .header-nav {
    display: flex;
  }
  .header-nav-wrap {
    display: block;
  }
}

@media (hover: hover) {
  a:hover > .underline {
    width: 100%;
    left: 0;
  }

  .header-nav > ul > li > a:hover {
    color: gray;
  }
}

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
</style>