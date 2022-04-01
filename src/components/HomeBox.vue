<template>
  <div id="Home" class="home-box"></div>
</template>

<script>
export default {};
</script>

<style scoped>
div {
  width: 100%;
  height: 100vh;
  background-color: cyan;
}

div::before {
  content: "";
  display: block;
  margin-top: -64px;
  height: 64px;
}
</style>