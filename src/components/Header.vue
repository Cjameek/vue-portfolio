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
  },
  data() {
    return {
      navItems: [
        {
          name: "About"
        },
        {
          name: "Experience"
        },
        {
          name: "Projects"
        },
        {
          name: "Contact"
        }
      ]
    };
  },
  methods: {
    createItemLink: function(id) {
      return "#" + id.toLowerCase();
    }
  }
};
</script>

<style lang="scss">
@import "../assets/scss/layout/_header.scss";
</style>
