<template>
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
</template>

<script>
export default {
  name: "Navigation",
  data() {
    return {
      navItems: [
        {
          name: "About"
        },
        {
          name: "Skills"
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

<style></style>
