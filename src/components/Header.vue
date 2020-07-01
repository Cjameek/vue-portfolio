<template>
  <header class="header">
    <figure class="header__icon rm">
      <img alt="Vue logo" src="../assets/img/logo.png" />
    </figure>
    <nav class="header__navigation">
      <ul class="header__navigation_menu">
        <li class="header__navigation_menu-item" v-for="item in navItems" :key="item.name">
          <a class="header__navigation_menu-item--link" :href="createItemLink(item.name)">{{ item.name }}</a>
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
          name: 'About'
        },
        {
          name: 'Experience'
        },
        {
          name: 'Projects'
        },
        {
          name: 'Contact'
        },
      ]
    }
  },
  methods: {
    createItemLink: function(id) {
      return '#' + id.toLowerCase();
    }
  }
}
</script>

<style lang="scss">
.header {
  background-color: var(--color-yellow);
  display: flex;
  position: relative;
  margin-bottom: 7.4rem;
  padding: 1.5rem 3rem;

  // &:before {
  //   content: '';
  //   background: rgb(255,255,255);
  //   background: linear-gradient(0deg, rgba(255,255,255,1) 20%, rgba(255,255,255,0) 100%);
  //   position: absolute;
  //   z-index: 5;
  //   top: 74px;
  //   left: 0;
  //   right: 0;
  //   width: 100%;
  //   height: 100%;
  //   transform: scaleY(.7);
  //   transform-origin: bottom;
  // }

  &:after {
    content: '';
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1440 320'%3E%3Cpath fill='%23FFCF99' fill-opacity='1' d='M0,128L1440,192L1440,0L0,0Z'%3E%3C/path%3E%3C/svg%3E");
    background-position: left;
    background-repeat: no-repeat;
    background-size: cover;
    position: absolute;
    z-index: 2;
    top: 100%;
    left: -20%;
    right: 0;
    width: calc(100% + 20%);
    height: 70px;
  }

  &__icon {
    img {
      max-width: 100px;
    }
  }

  &__navigation {
    align-self: center;
    margin-left: auto;

    &_menu-item {
      margin-right: 0;

      &--link {
        color: var(--color-dark);
        font-family: 'Lato', sans-serif;
        font-size: 20px;
        font-weight: 700;
        letter-spacing: 1.12px;
        text-decoration: none;
      }
    }

    &_menu-item + &_menu-item {
      margin-left: 2.4rem;
    }
  }
}
</style>