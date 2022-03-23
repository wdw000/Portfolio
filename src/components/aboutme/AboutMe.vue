<template>
  <h2>About Me</h2>
  <ul>
    <li v-for="(item, index) in items" :key="index">
      <about-me-item :item="item"></about-me-item>
    </li>
  </ul>
</template>

<script>
import AboutMeItem from "./AboutMeItem.vue";
export default {
  components: { AboutMeItem },
  data() {
    return {
      items: [
        { name: "이름", value: "왕도원" },
        { name: "생년월일", value: "98.02.20" },
        { name: "이메일", value: "dowonwang01@gmail.com" },
        { name: "학력", value: "동양미래대학교(컴퓨터정보공학과)" },
      ],
    };
  },
};
</script>

<style>
</style>