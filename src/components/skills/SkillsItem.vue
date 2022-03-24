<template>
  <div class="skills-item">
    <p>{{ item.title }}</p>
    <hr />
    <ul>
      <li v-for="(value, index) in item.titleItem" :key="index">
        {{ value }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    item: { type: Object, required: true },
  },
};
</script>

<style scoped>
.skills-item {
  font-size: 1.6rem;
  width: fit-content;
  border: solid black 1px;
  border-radius: 1em;
  padding: 1em;
}
</style>