<template>
  <div class="about-me-item">
    <img :src="require(`@/assets/img/${item.imgSrc}`)" alt="" />
    <dl>
      <dt>{{ item.name }}</dt>
      <dd v-html="item.value"></dd>
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
.about-me-item {
  display: flex;
  align-items: center;
  margin: 0 auto;
  width: 80%;
  font-size: 1.6rem;
}
dt {
  font-weight: bold;
  font-size: 1.2em;
  margin-bottom: 1rem;
}

img {
  margin: 1em;
}
</style>