<template>
  <div id="app">
    <Main msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Main
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,700;1,900&family=Roboto:wght@400;700&display=swap");

html {
  font-size: 62.5%; /* 10px browser default */
}

body {
  font-size: 16px;
}

#app {
  font-family: "Roboto", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Lato", sans-serif;
  font-weight: 900;
}

.rm {
  margin: 0;
}
</style>
