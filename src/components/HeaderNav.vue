<template>
  <nav class="header-nav" ref="headerNav" :class="{'header-scroll':isScroll}">
    <h1>Wang DoWon</h1>
    <ul>
      <li>About Me</li>
      <li>Skills</li>
      <li>Link</li>
      <li>Projects</li>
    </ul>
  </nav>

  <nav class="header-nav-small" ref="headerNavSmall" :class="{'header-scroll':isScroll}">
    <div>
      <h1>Wang DoWon</h1>
      <button @click="openMenu"></button>
    </div>
    <transition name="slide" appear>
      <ul v-if="menu" key="sample-key">
      <li>About Me</li>
      <li>Skills</li>
      <li>Link</li>
      <li>Projects</li>
    </ul>
    </transition>
    
  </nav>
</template>

<script>
export default {
  data() {
    return {
      menu: false,
      isScroll: false,
    };
  },
  mounted () {
    window.addEventListener('scroll', this.onScroll)
  },
  methods: {
    openMenu() {
      this.menu = !this.menu;
    },

    onScroll() {
      const currentScrollPosition = window.scrollY || document.documentElement.scrollTop;

      if(currentScrollPosition > 0) {
        this.isScroll = true;
      } else {
        this.isScroll = false;
      }
      
    }
  },
};
</script>

<style scoped>
.slide-enter-active, .slide-leave-active {
  transition: 0.5s ease-in;
}

.slide-enter-from { 
  height: 0;
}

.slide-enter-to{
  height: fit-content;
}

.header-nav-wrap,
.header-nav,
.header-nav-small {
  position: sticky;
  top: 0;
  left: 0;
  z-index: 100;
}

.header-scroll {
  background-color: white;
}

.header-nav {
  width: inherit;
  height: fit-content;
  max-width: 1300px;
  display: none;
  justify-content: space-between;
  margin: 0 auto;
  font-size: 2rem;
  padding: 2rem;
}

.header-nav > h1 {
  flex: 1;
}

.header-nav > ul {
  display: flex;
  align-items: center;
  flex: 1;
  transition: ;
}

.header-nav > ul > li {
  flex: 1;
  text-align: right;
}

.header-nav-small {
  width: inherit;
  max-width: 1300px;
  height: fit-content;
  margin: 0 auto;
  font-size: 2rem;
  padding: 2rem;

}

.header-nav-small > div {
  display: flex;
  justify-content: space-between;
}

.header-nav-small > ul {
  position: absolute;
  width: 100%;
  left: 0;
  background-color: #fff;
  padding: 2rem;
}

.header-nav-small > ul > li {
  margin: 2rem 0;
}

.header-nav-small > div > button {
  width: 24px;
  height: 24px;
  background-image: url('@/assets/img/round_menu_black_24dp.png');
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
}

@media (min-width: 719px) {
  .header-nav-small {
    display: none;
  }
  .header-nav {
    display: flex;
  }
}
</style>