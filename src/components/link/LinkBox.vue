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
          url: "github.com/wdw000",
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

<style>
</style>