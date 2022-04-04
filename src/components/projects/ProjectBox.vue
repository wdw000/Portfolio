<template>
  <div class="project-box" id="Projects">
    <h2>Projects</h2>
    <ul>
      <li><project-item></project-item></li>
    </ul>
  </div>
</template>

<script>
import ProjectItem from "./ProjectItem.vue";
export default {
  components: { ProjectItem },
};
</script>

<style scoped>
.project-box {
  width: inherit;
  max-width: 1300px;
  margin: 5rem auto;
}

.project-box::before {
  content: "";
  display: block;
  margin-top: -64px;
  padding-top: 64px;
}
</style>