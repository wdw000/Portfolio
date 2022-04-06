<template>
  <div class="skills-box component-box" id="Skills">
    <h2 hidden>Skills</h2>
    <ul>
      <li v-for="(item, index) in items" :key="index">
        <skills-item :item="item"></skills-item>
      </li>
    </ul>
  </div>
</template>

<script>
import SkillsItem from "./SkillsItem.vue";

export default {
  components: { SkillsItem },
  data() {
    return {
      items: [
        {
          class: "skill-skills",
          title: "Skills",
          titleItem: [
            {
              name: "HTML5",
              url: "https://upload.wikimedia.org/wikipedia/commons/3/38/HTML5_Badge.svg",
            },
            {
              name: "CSS3",
              url: "https://upload.wikimedia.org/wikipedia/commons/6/62/CSS3_logo.svg",
            },
            {
              name: "JavaScript",
              url: "https://upload.wikimedia.org/wikipedia/commons/6/6a/JavaScript-logo.png",
            },
            {
              name: "Vue.js",
              url: "https://upload.wikimedia.org/wikipedia/commons/9/95/Vue.js_Logo_2.svg",
            },
            {
              name: "jQuery",
              url: "https://upload.wikimedia.org/wikipedia/commons/8/81/JQuery_logo_text.svg",
            },

            {
              name: "Firebase",
              url: "https://upload.wikimedia.org/wikipedia/commons/3/37/Firebase_Logo.svg",
            },
          ],
        },
        {
          class: "skill-learning",
          title: "Learning",
          titleItem: [
            {
              name: "React.js",
              url: "https://upload.wikimedia.org/wikipedia/commons/4/47/React.svg",
            },
            {
              name: "TypeScript",
              url: "https://upload.wikimedia.org/wikipedia/commons/4/4c/Typescript_logo_2020.svg",
            },
          ],
        },
      ],
    };
  },
};
</script>

<style scoped>
.skills-box {
  font-size: 1rem;
  width: inherit;
  max-width: 1300px;
  margin: 0 auto;
}
.skills-box::before {
  content: "";
  display: block;
  margin-top: -64px;
  padding-top: 64px;
}
</style>