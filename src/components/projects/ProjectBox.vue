<template>
  <div class="project-box" id="Projects">
    <h2>Projects</h2>
    <ul>
      <li v-for="(item, index) in items" :key="index">
        <project-item :item="item"></project-item>
      </li>
    </ul>
  </div>
</template>

<script>
import ProjectItem from "./ProjectItem.vue";
export default {
  components: { ProjectItem },
  data() {
    return {
      items: [
        {
          title: "ToDo",
          imgSrc: "projects/todo.svg",
          url: {
            github: "https://github.com/wdw000/ToDo-Project",
            site: "site",
            pdf: "pdf",
          },
          used: "HTML, CSS, JavaScript, Vue, Firebase",
          functions: ["오늘의 할일 추가,삭제 및 수정", "지난 할일 통계"],
        },
        {
          title: "Portfolio",
          imgSrc: "home-title2.svg",
          url: { github: "https://github.com/wdw000/Portfolio", site: "site" },
          used: "HTML, CSS, JavaScript, Vue",
          functions: ["인적 사항, 기술 스택, 링크 및 프로젝트 정보 제공"],
        },
      ],
    };
  },
};
</script>

<style scoped>
.project-box {
  width: inherit;
  max-width: 1300px;
  padding: 0 2rem;
  margin: 5rem auto;
}

.project-box::before {
  content: "";
  display: block;
  margin-top: -64px;
  padding-top: 64px;
}

ul > li {
  margin-bottom: 5rem;
}
</style>