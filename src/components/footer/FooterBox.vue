<template>
  <div class="footer-box">
      <footer-item></footer-item>
  </div>
</template>

<script>
import FooterItem from "./FooterItem.vue";

export default {
    components: { FooterItem },
}
</script>

<style scoped>
.footer-box {
    width: 100%;
    height: 10rem;
    background-color: gray;
}
</style>