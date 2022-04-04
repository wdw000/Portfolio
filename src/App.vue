<template>
  <home-box></home-box>
  <header-nav></header-nav>
  <about-me></about-me>
  <skills-box></skills-box>
  <link-box></link-box>
  <project-box></project-box>
  <div class="test"></div>
</template>

<script>
import AboutMe from "./components/aboutme/AboutMe.vue";
import HeaderNav from "./components/HeaderNav.vue";
import HomeBox from "./components/HomeBox.vue";
import LinkBox from "./components/link/LinkBox.vue";
import ProjectBox from "./components/projects/ProjectBox.vue";
import SkillsBox from "./components/skills/SkillsBox.vue";

export default {
  name: "App",
  components: { AboutMe, SkillsBox, LinkBox, HeaderNav, HomeBox, ProjectBox },

  methods: {},
};
</script>
<style>
@import url("./assets/css/reset.css");

html {
  font-size: 10px;
  font-family: sans-serif;
  scroll-behavior: smooth;
}

* {
  box-sizing: border-box;
}

h2,
h3 {
  text-align: center;
  font-size: 2.5rem;
  margin: 2rem 0;
}

@media (min-width: 600px) {
  h2,
  h3 {
    font-size: 2.75rem;
    margin: 2rem 0;
  }
}

@media (min-width: 992px) {
  h2,
  h3 {
    font-size: 3rem;
  }
}

.hidden {
  font-size: 0;
}

.test {
  height: 100vh;
  background-color: gray;
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
</style>
