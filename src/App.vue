<template>
  <header-nav></header-nav>
  <home-box></home-box>
  <about-me></about-me>
  <skills-box></skills-box>
  <link-box></link-box>
  <div class="test"></div>
</template>

<script>
import AboutMe from "./components/aboutme/AboutMe.vue";
import HeaderNav from "./components/HeaderNav.vue";
import HomeBox from "./components/HomeBox.vue";
import LinkBox from "./components/link/LinkBox.vue";
import SkillsBox from "./components/skills/SkillsBox.vue";

export default {
  name: "App",
  components: { AboutMe, SkillsBox, LinkBox, HeaderNav, HomeBox },

  methods: {},
};
</script>
<style>
@import url("./assets/css/reset.css");

html {
  font-size: 10px;
}

* {
  box-sizing: border-box;
}

h2,
h3 {
  font-weight: bold;
  text-align: center;
  font-size: 2rem;
}

.hidden {
  font-size: 0;
}

.test {
  height: 100vh;
  background-color: gray;
}
</style>
