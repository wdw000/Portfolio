<template>
  <article class="project-item-small">
    <div class="project-small-inner">
      <transition name="opacity">
        <div class="project-small-content" v-if="showContent">
          <h3>{{item.title}}</h3>
          <dl>
            <dt>Functions</dt>
            <dd v-for="(list, index) in item.functions" :key="index">
              {{list}}
            </dd>
            <dt>Skills</dt>
            <dd>{{item.used}}</dd>
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
      </transition>
      <transition name="opacity">
        <div class="project-small-img" v-if="!showContent">
          <img :src="require(`@/assets/${item.imgSrc}`)" />
        </div>
      </transition>
    </div>
    <div class="project-small-more" @click="isShow">MORE</div> 
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
    }
  },
  methods: {
    isShow() {
      this.showContent = !this.showContent;
    }
  }
};
</script>

<style scoped>
h3 {
  margin: 0;
  padding-bottom: 1rem;
  font-size: 2rem;
  font-weight: bold;
  border-bottom: solid 2px lightgray;
}

dt,p {
  font-weight: bold;
  font-size: 1.2em;
  margin: 1rem 0;
}

dd {
  margin: 1rem 0;
}

dd, ul {
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
  width: 4rem;
  height: 4rem;
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center;
}

.project-item-small {
  background-color: #f6f4f2;
  font-size: 1.6rem;
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

/* transiton */
.opacity-enter-active {
  transition: all 0.5s ease-in;
}

.opacity-enter-from {
  opacity: 0;
}

.opacity-enter-to {
  opacity: 1;
}
</style>