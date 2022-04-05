<template>
  <div class="footer-box">
    <div>
      <ul>
        <a href="http://github.com/wdw000" target="_blank">
          <li class="footer-github"></li
        ></a>
        <a href="mailto:dowonwang01@gmail.com"
          ><li class="footer-email"></li
        ></a>
      </ul>
      <p>Thank you for visiting my portfolio.</p>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
};
</script>

<style scoped>
.footer-box {
  width: 100%;
  background-color: #222222;
  font-size: 1.6rem;
  color: white;
  padding: 2rem;
}

.footer-box > div {
  width: inherit;
  max-width: 1300px;
  margin: 0 auto;
}

ul {
  display: flex;
  justify-content: center;
}

li {
  margin: 0 1rem;
  width: 6rem;
  height: 6rem;
  background-color: white;
  border: solid white 2px;
  border-radius: 6rem;
}

p {
  text-align: center;
  margin-top: 2rem;
}

.footer-github,
.footer-email {
  background-position: center;
  background-repeat: no-repeat;
  background-size: contain;
}

.footer-github {
  background-image: url("https://upload.wikimedia.org/wikipedia/commons/9/91/Octicons-mark-github.svg");
}

.footer-email {
  background-image: url("@/assets/img/email_black_24dp.svg");
}
</style>