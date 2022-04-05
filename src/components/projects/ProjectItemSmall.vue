<template>
  <article class="project-item-small">
    <div class="project-small-inner">
      <img :src="require(`@/assets/${item.imgSrc}`)" />
    </div>
    <button>더보기</button>
  </article>
</template>

<script>
export default {
  props: {
    item: { type: Object, required: true },
  },
};
</script>

<style scoped>
.project-item-small * {
  border: solid black 1px;
}

.project-item-small {
  width: 100%;
  position: relative;
  max-width: 350px;
  font-size: 1.6rem;
  background-color: #f6f4f2;
  margin: 0 auto;
}

.project-item-small::after {
  padding-bottom: 100%;
  display: block;
  content: "";
}

.project-item-small > button {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
}

.project-small-inner {
  position: absolute;
  width: 80%;
  height: 80%;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #fff;
}

.project-small-inner > img {
  position: absolute;
  width: 95%;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>