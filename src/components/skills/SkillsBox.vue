<template>
  <h2>Skills</h2>
  <div class="skills">
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
          title: "Frontend",
          titleItem: ["HTML5", "CSS3", "JavaScript", "Vue.js"],
        },
        { title: "Backend", titleItem: ["Node.js"] },
      ],
    };
  },
};
</script>

<style>
</style>