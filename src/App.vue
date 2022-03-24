<template>
  <header-nav></header-nav>
  <about-me></about-me>
  <skills-box></skills-box>
</template>

<script>
import AboutMe from "./components/aboutme/AboutMe.vue";
import HeaderNav from "./components/HeaderNav.vue";
import SkillsBox from "./components/skills/SkillsBox.vue";

export default {
  name: "App",
  components: { HeaderNav, AboutMe, SkillsBox },
};
</script>

<style>
</style>
