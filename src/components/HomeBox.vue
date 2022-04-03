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

.scroll-down {
  position: absolute;
  bottom: 5%;
  left: 50%;
  font-size: 3rem;
  transform: translate(-50%, 0);
  transform: rotate(90deg);
  animation: down infinite 1s alternate;
}

/* trasition */
.slide-fade-enter-active {
  transition: all 0.6s ease-in-out;
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateY(50px);
  opacity: 0;
}

/* animation */

@keyframes down {
  from {
    bottom: 5%;
  }

  to {
    bottom: 2%;
  }
}
</style>