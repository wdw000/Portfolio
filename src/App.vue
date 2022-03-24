<template>
  <header-nav></header-nav>
  <about-me></about-me>
  <skills-box></skills-box>
  <link-box></link-box>
</template>

<script>
import AboutMe from "./components/aboutme/AboutMe.vue";
import HeaderNav from "./components/HeaderNav.vue";
import LinkBox from "./components/link/LinkBox.vue";
import SkillsBox from "./components/skills/SkillsBox.vue";

export default {
  name: "App",
  components: { HeaderNav, AboutMe, SkillsBox, LinkBox },
};
</script>

<style>
</style>
