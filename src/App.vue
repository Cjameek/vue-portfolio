<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,700;1,900&family=Roboto:wght@400;700&display=swap");

:root {
  --color-light: #eeeeee;
  --color-dark: #040f16;
  --color-red: #c83d28;
  --color-blue: #5171a5;
  --color-yellow: #ffcf99;
  --color-green: #e4f1e6;
  --font-body: "Roboto", sans-serif;
  --font-heading: "Lato", sans-serif;
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
