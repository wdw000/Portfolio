<template>
  <div id="Home" class="home-box">
    <div class="home-wrap">
      <div class="home-title">
        <transition name="slide-fade" appear>
          <div></div>
        </transition>
      </div>
      <div class="scroll-down">></div>
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
  position: relative;
}

.home-title {
  height: 100vh;
  padding: 1rem;
}

.home-title > div {
  width: 100%;
  height: 100%;
  background-image: url("../assets/home-title2.svg");
  background-repeat: no-repeat;
  background-position: center left;
  background-size: contain;
}

.scroll-down {
  position: absolute;
  color: gray;
  bottom: 10%;
  left: 50%;
  font-size: 5rem;
  font-weight: bold;
  transform: rotate(90deg) translateX(-50%);
  animation: down infinite 1s alternate;
}

@media (min-width: 800px) {
  .home-box,
  .home-title {
    height: calc(100vh - 64px);
  }

  .scroll-down {
    display: none;
  }
}

/* trasition */
.slide-fade-enter-active {
  transition: all 0.6s ease-in-out;
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateY(50px);
  filter: blur(3px);
  opacity: 0;
}

/* animation */

@keyframes down {
  from {
    bottom: 10%;
  }

  to {
    bottom: 5%;
  }
}
</style>