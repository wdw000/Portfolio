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
</template>

<script>
export default {};
</script>

<style scoped>
.header-nav {
  width: inherit;
  height: fit-content;
  max-width: 1300px;
  display: flex;
  justify-content: space-between;
  margin: 0 auto;
  font-size: 2rem;
}

.header-nav-wrap,
.header-nav {
  position: sticky;
  top: 0;
  left: 0;
}

.header-nav > h1 {
  margin: 1em;
}

.header-nav > ul {
  display: flex;
  align-items: center;
  margin: 1em;
  width: 40%;
}

.header-nav > ul > li {
  flex: 1;
  text-align: center;
}
</style>