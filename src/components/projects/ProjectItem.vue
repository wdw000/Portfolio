<template>
  <article class="project-item">
    <div class="project-item-img">img</div>
    <div class="project-item-content">
      <h3>title</h3>
      <p>주요기능</p>
      <p>사용한거</p>
      <p>url</p>
    </div>
  </article>
</template>

<script>
export default {};
</script>

<style scoped>
.project-item * {
  border: solid black 1px;
}

.project-item {
  display: flex;
  background-color: #f6f4f2;
}

.project-item > div {
  flex: 1;
}
</style>