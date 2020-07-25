<template>
  <div id="app">
    <Main />
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

p {
  line-height: 1.6;
}

.rm {
  margin: 0;
}
</style>
