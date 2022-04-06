<template>
  <div class="link-item">
    <a :href="`https://${item.url}`" target="_blank">
      <div :class="['link-wrap', item.class]">
        <div
          class="link-inner item-hover"
          :style="{ 'background-image': `url(${item.imgSrc}` }"
        ></div>
      </div>
      <p class="link-img">{{ item.title }}</p></a
    >
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
.link-wrap {
  width: 100%;
  background-color: #f6f4f2;
  position: relative;
}

.link-wrap::after {
  padding-bottom: 100%;
  display: block;
  content: "";
}

.link-inner {
  position: absolute;
  width: 80%;
  height: 80%;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-size: contain;
  background-origin: content-box;
  background-repeat: no-repeat;
  background-position: center;
}

p {
  text-align: center;
  margin-top: 1rem;
  font-size: 0.7em;
}
</style>