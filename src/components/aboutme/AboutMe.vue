<template>
  <div class="about-me" id="AboutMe">
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
          class: "name",
          name: "이름",
          value: "왕도원",
          imgSrc: "round_person_black_24dp_2x.png",
        },
        {
          class: "birth",
          name: "생년월일",
          value: "98.02.20",
          imgSrc: "round_calendar_today_black_24dp_2x.png",
        },
        {
          class: "school",
          name: "학력",
          value: "동양미래대학교<br>(컴퓨터정보공학과)",
          imgSrc: "round_edit_black_24dp_2x.png",
        },
        {
          class: "email",
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
  margin: 5rem auto;
}

.about-me::before {
  content: "";
  display: block;
  margin-top: -64px;
  padding-top: 64px;
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