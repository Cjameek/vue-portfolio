<template>
  <div class="hero hero__wrapper">
    <h1 class="abs-center">{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: "Hero",
  data() {
    return {
      msg: "This is a test message"
    };
  }
};
</script>

<style lang="scss">
@import "../assets/scss/components/_hero.scss";
</style>
