<template>
  <header-nav></header-nav>
  <about-me></about-me>
</template>

<script>
import AboutMe from "./components/aboutme/AboutMe.vue";
import HeaderNav from "./components/HeaderNav.vue";
export default {
  name: "App",
  components: { HeaderNav, AboutMe },
};
</script>

<style>
</style>
