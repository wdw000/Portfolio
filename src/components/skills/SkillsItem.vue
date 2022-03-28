<template>
  <article class="skills-item">
    <h3>{{ item.title }}</h3>
    <hr />
    <div :class="['skill-wrap', item.class, 'graybox']">
      <article
        v-for="(value, index) in item.titleItem"
        :key="index"
        class="skill-square"
      >
        <h4 class="hidden">{{ value.name }}</h4>
        <div
          class="inner"
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
.skills-item {
  font-size: 1.6rem;
  width: inherit;
  max-width: 1300px;
  margin: 0 auto;
}

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