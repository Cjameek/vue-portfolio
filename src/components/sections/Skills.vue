<template>
  <div class="skills__container">
    <h2 class="skills__subtitle">This should be fun</h2>
  </div>
</template>

<script>
export default {
  name: "Skills",
  data() {
    return {
      skills: [
        {
          name: "Vue"
        },
        {
          name: "Vue"
        },
        {
          name: "Vue"
        },
        {
          name: "Vue"
        },
        {
          name: "Vue"
        },
        {
          name: "Vue"
        },
        {
          name: "Vue"
        }
      ]
    };
  }
};
</script>

<style lang="scss">
.skills {
  &__container {
    display: flex;
    flex-direction: column;
  }
}
</style>
