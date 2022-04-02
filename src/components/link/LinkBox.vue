<template>
  <div class="link-box component-box" id="Link">
    <h2>Link</h2>
    <ul>
      <li v-for="(item, index) in items" :key="index">
        <link-item :item="item"></link-item>
      </li>
    </ul>
  </div>
</template>

<script>
import LinkItem from "./LinkItem.vue";
export default {
  components: { LinkItem },
  data() {
    return {
      items: [
        {
          title: "github",
          class: "link-github",
          url: "github.com/wdw000",
          imgSrc:
            "https://upload.wikimedia.org/wikipedia/commons/9/91/Octicons-mark-github.svg",
        },
      ],
    };
  },
};
</script>

<style scoped>
.link-box {
  width: inherit;
  max-width: 1300px;
  margin: 5rem auto;
  font-size: 1.6rem;
}

@media (min-width: 600px) {
  .link-box {
    font-size: 2rem;
  }
}

@media (min-width: 992px) {
  .link-box {
    font-size: 2.5rem;
  }
}

.link-box::before {
  content: "";
  display: block;
  margin-top: -64px;
  padding-top: 64px;
}

ul {
  width: inherit;
  display: flex;
  justify-content: space-evenly;
}

li {
  width: 20%;
}
</style>