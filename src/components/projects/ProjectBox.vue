<template>
  <div class="project-box" id="Projects">
    <h2 class="title">Projects</h2>
    <!-- 프로젝트 큰화면 -->
    <ul class="project-wide">
      <li v-for="(item, index) in items" :key="index">
        <project-item :item="item"></project-item>
      </li>
    </ul>
    <!-- 프로젝트 작은 화면 -->
    <ul class="project-small">
      <li v-for="(item, index) in items" :key="index">
        <project-item-small :item="item"></project-item-small>
      </li>
    </ul>
  </div>
</template>

<script>
import ProjectItem from "./ProjectItem.vue";
import ProjectItemSmall from "./ProjectItemSmall.vue";
export default {
  components: { ProjectItem, ProjectItemSmall },
  data() {
    return {
      items: [
        {
          title: "ToDo",
          imgSrc: "projects/todo.svg",
          url: {
            github: "https://github.com/wdw000/ToDo-Project",
            site: "https://todo-e4862.web.app/login",
            pdf: "https://drive.google.com/file/d/1kDDm_3BDMCf-dmAKy80CIsWbvRFSqbsX/view?usp=sharing",
          },
          used: "HTML, CSS, JavaScript, Vue, Firebase",
          functions: ["-오늘의 할일 추가,삭제 및 수정", "-지난 할일 통계"],
        },
        {
          title: "Portfolio",
          imgSrc: "home-title2.svg",
          url: {
            github: "https://github.com/wdw000/Portfolio",
            site: "https://wdw000.github.io",
            pdf: "https://drive.google.com/file/d/1QCb3JU7HlmirJNFeu3E1xhRX1T_Rcvh2/view?usp=sharing",
          },
          used: "HTML, CSS, JavaScript, Vue",
          functions: ["-인적 사항, 기술 스택, 링크 및 프로젝트 정보 제공"],
        },
      ],
    };
  },
};
</script>

<style scoped>
ul > li {
  margin-bottom: 5rem;
}
.project-box {
  width: inherit;
  max-width: 1300px;
  padding: 0 2rem;
  margin: 5rem auto;
  font-size: 1rem;
}

.project-box::before {
  content: "";
  display: block;
  margin-top: -64px;
  padding-top: 64px;
}

.project-wide {
  display: none;
}

.project-small {
  display: block;
}

@media (min-width: 800px) {
  .project-wide {
    display: block;
  }

  .project-small {
    display: none;
  }
}
</style>