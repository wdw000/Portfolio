<template>
  <h2>Link</h2>
  <div class="link-box">
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
          contents: [
            "공부하면서 끄적였던 소스들",
            "각종 튜토리얼들",
            "프로젝트들",
          ],
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

ul {
  width: inherit;
  display: flex;
  justify-content: space-evenly;
}

li {
  width: 20%;
}
</style>