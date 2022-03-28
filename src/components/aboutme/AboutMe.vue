<template>
  <div class="about-me">
    <h2>About Me</h2>
    <ul>
      <li v-for="(item, index) in items" :key="index">
        <about-me-item :item="item"></about-me-item>
      </li>
    </ul>
  </div>
</template>

<script>
import AboutMeItem from "./AboutMeItem.vue";
export default {
  components: { AboutMeItem },
  data() {
    return {
      items: [
        {
          name: "이름",
          value: "왕도원",
          imgSrc: "round_person_black_24dp_2x.png",
        },
        {
          name: "생년월일",
          value: "98.02.20",
          imgSrc: "round_calendar_today_black_24dp_2x.png",
        },
        {
          name: "학력",
          value: "동양미래대학교<br>(컴퓨터정보공학과)",
          imgSrc: "round_edit_black_24dp_2x.png",
        },
        {
          name: "이메일",
          value: "dowonwang01@gmail.com",
          imgSrc: "round_email_black_24dp_2x.png",
        },
      ],
    };
  },
};
</script>

<style scoped>
.about-me {
  width: inherit;
  max-width: 1300px;
  margin: 0 auto;
}

ul {
  display: flex;
  flex-flow: row wrap;
  align-items: center;
  margin: 0 auto;
}

li {
  width: 100%;
}

@media (min-width: 600px) {
  li {
    width: 50%;
  }
}

@media (min-width: 992px) {
  li {
    width: 25%;
  }
}
</style>