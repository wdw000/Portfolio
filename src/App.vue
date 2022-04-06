<template>
  <home-box></home-box>
  <header-nav></header-nav>
  <about-me></about-me>
  <skills-box></skills-box>
  <link-box></link-box>
  <project-box></project-box>
  <footer-box></footer-box>
</template>

<script>
import AboutMe from "./components/aboutme/AboutMe.vue";
import FooterBox from "./components/footer/FooterBox.vue";
import HeaderNav from "./components/HeaderNav.vue";
import HomeBox from "./components/HomeBox.vue";
import LinkBox from "./components/link/LinkBox.vue";
import ProjectBox from "./components/projects/ProjectBox.vue";
import SkillsBox from "./components/skills/SkillsBox.vue";

export default {
  name: "App",
  components: {
    AboutMe,
    SkillsBox,
    LinkBox,
    HeaderNav,
    HomeBox,
    ProjectBox,
    FooterBox,
  },
};
</script>
<style>
@import url("./assets/css/reset.css");
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans&family=Noto+Sans+KR&display=swap");

html {
  font-size: 12px;
  font-family: "Noto Sans", "Noto Sans KR", sans-serif;
  scroll-behavior: smooth;
}

* {
  box-sizing: border-box;
}

.title {
  text-align: center;
  font-size: 1.5em;
  margin: 2rem 0;
  font-weight: bold;
}

.hidden {
  font-size: 0;
}

.link-img::after {
  content: "";
  height: 0.9em;
  width: 0.9em;
  display: inline-block;
  margin-left: 5px;
  background-image: url("@/assets/img/external.svg");
  background-position: center;
  background-repeat: no-repeat;
  background-size: contain;
}

@media (hover: hover) {
  .item-hover:hover {
    filter: blur(2px) grayscale(1);
  }
}

@media (min-width: 320px) {
  html {
    font-size: 13px;
  }
}

@media (min-width: 425px) {
  html {
    font-size: 14px;
  }
}

@media (min-width: 768px) {
  html {
    font-size: 16px;
  }
}
</style>
