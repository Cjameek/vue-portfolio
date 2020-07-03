<template>
  <header class="header">
    <figure class="header__icon rm">
      <img alt="Vue logo" src="../assets/img/logo.png" />
    </figure>
    <Navigation />
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
