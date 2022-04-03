<template>
  <div id="Home" class="home-box">
    <div class="home-wrap">
      <div class="home-title">
        <div></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.home-box {
  width: 100%;
  height: 100vh;
  background-color: #f6f4f2;
}

.home-wrap {
  width: inherit;
  max-width: 1300px;
  margin: 0 auto;
}

.home-title {
  height: 100vh;
  padding: 5rem;
}

.home-title > div {
  width: 100%;
  height: 100%;
  background-image: url("../assets/home-title2.svg");
  background-repeat: no-repeat;
  background-position: center left;
  background-size: contain;
}
</style>