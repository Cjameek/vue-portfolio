<template>
  <div class="hero hero__wrapper">
    <div class="abs-center">
      <h1>{{ title }}</h1>
      <h2>{{ subtitle }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: "Hero",
  data() {
    return {
      title: "Hey, my name is Cody Meek",
      subtitle: "But if you got this far, you probably already knew that..."
    };
  }
};
</script>

<style lang="scss">
@import "../assets/scss/components/_hero.scss";
</style>
