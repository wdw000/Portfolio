<template>
  <div class="link-item">
    <dl>
      <div class="link-title">
        <img :src="item.imgSrc" />
        <div>
          <dt>{{ item.title }}</dt>
          <a :href="`https://${item.url}`" target="_blank">
            <dd>{{ item.url }}</dd>
          </a>
        </div>
      </div>
      <dd
        v-for="(value, index) in item.contents"
        :key="index"
        class="link-content"
      >
        {{ value }}
      </dd>
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
  width: 45%;
  margin: 0 auto;
  border: solid black 1px;
  padding: 1em;
}

.link-title {
  display: flex;
  padding: 1rem;
}

img {
  width: 10%;
  margin-right: 1rem;
}
</style>