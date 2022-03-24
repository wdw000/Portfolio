<template>
  <div class="link-item">
    <dl>
      <dt>{{ item.title }}</dt>
      <dd>{{ item.url }}</dd>
      <dd v-for="(value, index) in item.contents" :key="index">{{ value }}</dd>
    </dl>
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