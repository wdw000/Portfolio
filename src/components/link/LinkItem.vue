<template>
  <div class="link-item">
    <dl>
      <dt>{{ item.title }}</dt>
      <dd>{{ item.url }}</dd>
      <hr />
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

<style scoped>
.link-item {
  font-size: 1.6rem;
  width: fit-content;
  padding: 1em;
  border: solid black 1px;
  border-radius: 1em;
}
</style>