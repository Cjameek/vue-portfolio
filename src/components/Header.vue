<template>
  <header class="header">
    <div class="header__wrapper">
      <figure class="header__icon rm">
        <img alt="Vue logo" src="../assets/img/logo.png" />
      </figure>
      <Navigation />
    </div>

    <!-- <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
      <path
        fill="#FFFFFF"
        fill-opacity="1"
        d="M0,128L1440,160L1440,0L0,0Z"
      ></path>
    </svg> -->
  </header>
</template>

<script>
import Navigation from "./Navigation";
export default {
  name: "Header",
  components: {
    Navigation
  }
};
</script>

<style lang="scss">
@import "../assets/scss/layout/_header.scss";
</style>
