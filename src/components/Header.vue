<template>
  <header class="header">
    <figure class="header__icon rm">
      <img alt="Vue logo" src="../assets/img/logo.png" />
    </figure>
    <nav class="header__navigation">
      <ul class="header__navigation_menu">
        <li
          class="header__navigation_menu-item"
          v-for="item in navItems"
          :key="item.name"
        >
          <a
            class="header__navigation_menu-item--link"
            :href="createItemLink(item.name)"
            >{{ item.name }}</a
          >
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: "Header",
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
