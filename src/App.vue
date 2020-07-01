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
@import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,700;1,900&family=Roboto:wght@400;700&display=swap');

:root {
  --color-light: #eeeeee;
  --color-dark: #040F16;
  --color-red: #D64933;
  --color-blue: #5171A5;
  --color-yellow: #FFCF99;
  --color-green: #E4F1E6;
}

#app {
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
h1,h2,h3,h4,h5,h6 {
  font-family: 'Lato', sans-serif;
  font-weight: 900;
}

.rm {
  margin: 0;
}
</style>
