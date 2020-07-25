<template>
  <section :id="sectionShow">
    <slot name="sectionTitle">Title</slot>
    <About v-if="section === 'about'" />
    <Skills v-if="section === 'skills'" />
  </section>
</template>

<script>
import About from "./sections/About";
import Skills from "./sections/Skills";

export default {
  name: "Section",
  components: {
    About,
    Skills
  },
  props: {
    sectionShow: String,
    contentBody: Object
  },
  data() {
    return {
      content: this.contentBody,
      section: this.sectionShow
    };
  },
  computed: {
    logCurrentContent: function() {
      return console.log(this.content);
    }
  }
};
</script>

<style lang="scss">
@import "../assets/scss/components/_sections.scss";
</style>
