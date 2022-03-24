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

<style>
</style>