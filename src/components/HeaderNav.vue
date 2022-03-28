<template>
  <nav class="header-nav">
    <h1>Wang DoWon</h1>
    <ul>
      <li>About Me</li>
      <li>Skills</li>
      <li>Link</li>
      <li>Projects</li>
    </ul>
  </nav>

  <nav class="header-nav-small">
    <div>
      <h1>Wang DoWon</h1>
      <button @click="openMenu">menu</button>
    </div>

    <ul v-show="menu">
      <li>About Me</li>
      <li>Skills</li>
      <li>Link</li>
      <li>Projects</li>
    </ul>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      menu: false,
      scrollTop: 0,
    };
  },

  methods: {
    openMenu() {
      this.menu = !this.menu;
    },
  },
};
</script>

<style scoped>
.header-nav-wrap,
.header-nav,
.header-nav-small {
  position: sticky;
  top: 0;
  left: 0;
  z-index: 100;
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
}

.header-nav-small > div {
  display: flex;
  justify-content: space-between;
  margin: 2rem;
}

.header-nav-small > ul {
  position: absolute;
  width: 100%;
  background-color: #fff;
  padding: 2rem;
}

.header-nav-small > ul > li {
  margin: 2rem 0;
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