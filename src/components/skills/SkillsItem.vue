<template>
  <article class="skills-item">
    <h3>{{ item.title }}</h3>
    <hr />
    <div :class="['skill-wrap', item.class]">
      <article
        v-for="(value, index) in item.titleItem"
        :key="index"
        :class="['skill-square', `${item.class}-square`]"
      >
        <h4 class="hidden">{{ value.name }}</h4>
        <div
          class="inner item-hover"
          :style="{ 'background-image': `url(${value.url})` }"
        ></div>
      </article>
    </div>
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
.skill-wrap {
  display: grid;
}

.skill-skills {
  grid-template-columns: repeat(2, 1fr);
}

.skill-learning {
  grid-template-columns: repeat(1, 1fr);
}

@media (min-width: 600px) {
  .skill-skills {
    grid-template-columns: repeat(3, 1fr);
  }

  .skill-learning {
    grid-template-columns: repeat(2, 1fr);
  }
}

.skill-square {
  width: 85%;
  margin-bottom: 15%;
  margin-left: 7.5%;
  margin-right: 7.5%;
  background-color: #f6f4f2;
  position: relative;
}

.skill-square::after {
  padding-bottom: 100%;
  display: block;
  content: "";
}

.skills-item:nth-child(1) {
  margin-bottom: 5rem;
}

.skill-skills-square:nth-child(n + 5) {
  margin-bottom: 0;
}

.skill-learning-square:nth-child(n + 2) {
  margin-bottom: 0;
}

@media (min-width: 600px) {
  .skill-skills-square:nth-child(n + 4) {
    margin-bottom: 0;
  }

  .skill-learning-square:nth-child(n + 1) {
    margin-bottom: 0;
  }
}

.inner {
  position: absolute;
  width: 80%;
  height: 80%;
  background-size: contain;
  background-origin: content-box;
  background-repeat: no-repeat;
  background-position: center;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>