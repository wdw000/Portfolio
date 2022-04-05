<template>
  <article class="project-item">
    <div class="project-item-img">
      <img :src="require(`@/assets/${item.imgSrc}`)" />
    </div>
    <div class="project-item-content">
      <h3>{{ item.title }}</h3>
      <dl>
        <dt>Functions</dt>
        <dd v-for="(list, index) in item.functions" :key="index">
          {{ list }}
        </dd>
        <dt>Skills</dt>
        <dd>{{ item.used }}</dd>
      </dl>
      <p>Link</p>
      <ul>
        <a :href="item.url.github" target="_blank" v-if="item.url.github"
          ><li>
            <div class="project-git"></div>
            <div class="link-img">github</div>
          </li></a
        >

        <a :href="item.url.site" target="_blank" v-if="item.url.site">
          <li>
            <div class="project-site"></div>
            <div class="link-img">site</div>
          </li></a
        >

        <a :href="item.url.pdf" target="_blank" v-if="item.url.pdf">
          <li>
            <div class="project-pdf"></div>
            <div class="link-img">pdf</div>
          </li></a
        >
      </ul>
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
h3 {
  margin: 0;
  border-bottom: lightgrey solid 2px;
  font-weight: bold;
}

dt,
p {
  font-size: 1.2em;
  font-weight: bold;
  margin-top: 2rem;
}

dd {
  margin: 1rem 0;
  margin-left: 1rem;
}
/* 
.project-item * {
  border: solid black 1px;
} */

.project-item {
  display: flex;
  background-color: #f6f4f2;
  font-size: 1.6rem;
}

@media (min-width: 1000px) {
  .project-item {
    font-size: 2rem;
  }
}

.project-item > div {
  flex: 1;
}

.project-item-img {
  position: relative;
  width: 100%;
}

.project-item-img::after {
  padding-bottom: 100%;
  display: block;
  content: "";
}

.project-item-img > img {
  position: absolute;
  padding: 5rem;
  width: 80%;
  height: 80%;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #fff;
}

.project-img-inner > img {
  height: 100%;
}

.project-item-content {
  padding: 4%;
}

ul {
  display: flex;
  margin-left: 1rem;
  margin-top: 1rem;
}

li {
  margin-right: 3rem;
}

li > div[class*="project"] {
  width: 6rem;
  height: 6rem;
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center;
}

li > div[class*="project"] + div {
  text-align: center;
}

.project-git {
  background-image: url("https://upload.wikimedia.org/wikipedia/commons/9/91/Octicons-mark-github.svg");
}

.project-site {
  background-image: url("../../assets/img/language_black_24dp.svg");
}

.project-pdf {
  background-image: url("../../assets/img/picture_as_pdf_black_24dp.svg");
}
</style>