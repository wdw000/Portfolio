<template>
  <div class="link-box" id="Link">
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
  margin: 0 auto;
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