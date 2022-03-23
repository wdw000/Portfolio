<template>
  <div class="about-me-item">
    <dt>{{ item.name }}</dt>
    <dd>{{ item.value }}</dd>
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