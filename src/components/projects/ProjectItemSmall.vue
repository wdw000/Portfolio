<template>
  <article class="project-item-small">
    <div class="project-small-inner">
      <div class="project-small-content" v-if="showContent">
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
              <div class="link-img">GITHUB</div>
            </li></a
          >

          <a :href="item.url.site" target="_blank" v-if="item.url.site">
            <li>
              <div class="project-site"></div>
              <div class="link-img">WEB</div>
            </li></a
          >

          <a :href="item.url.pdf" target="_blank" v-if="item.url.pdf">
            <li>
              <div class="project-pdf"></div>
              <div class="link-img">PDF</div>
            </li></a
          >
        </ul>
      </div>

      <div class="project-small-img" v-if="!showContent">
        <img :src="require(`@/assets/${item.imgSrc}`)" />
      </div>
    </div>
    <div class="project-small-more" @click="isShow">
      {{ showContent ? "IMG" : "MORE" }}
    </div>
  </article>
</template>

<script>
export default {
  props: {
    item: { type: Object, required: true },
  },
  data() {
    return {
      showContent: false,
    };
  },
  methods: {
    isShow() {
      this.showContent = !this.showContent;
    },
  },
};
</script>

<style scoped>
h3 {
  padding-bottom: 1rem;
  margin: 1rem 0;
  font-size: 1.4em;
  font-weight: bold;
  text-align: center;
  border-bottom: solid 2px lightgray;
}

dt,
p {
  font-weight: bold;
  font-size: 1.2em;
  margin: 1rem 0;
}

dd {
  margin: 1rem 0;
}

dd,
ul {
  margin-left: 1rem;
}

ul {
  display: flex;
}

ul > a {
  flex: 1;
}

li {
  display: flex;
  flex-direction: column;
  align-items: center;
}

li > div[class*="project"] {
  width: 3.5rem;
  height: 3.5rem;
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center;
}

li > div[class*="project"] + div {
  font-size: 0.8em;
}

.project-item-small {
  background-color: #f6f4f2;
  padding: 2rem;
  padding-bottom: 0;
  max-width: 350px;
  margin: 0 auto;
}

.project-small-inner {
  background-color: #fff;
  height: fit-content;
  padding: 1rem;
}

.project-small-more {
  text-align: center;
  padding: 1rem;
  cursor: pointer;
  text-decoration: underline;
  font-size: 1.2em;
}

.project-small-img {
  position: relative;
  width: 100%;
}

.project-small-img::after {
  padding-bottom: 100%;
  display: block;
  content: "";
}

.project-small-img > img {
  position: absolute;
  width: 100%;
  height: 100%;
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