<template>
  <main class="primary-content">
    <Header />
    <Hero />
    <Footer />
  </main>
</template>

<script>
import Header from "./Header";
import Hero from "./Hero";
import Footer from "./Footer";
import axios from "axios";

export default {
  components: {
    Header,
    Hero,
    Footer
  },
  name: "Main",
  props: {
    msg: String
  },
  data() {
    return {
      posts: [],
      totalPages: 1,
      currentPage: 1,
      errors: []
    };
  },
  methods: {
    getPrismicPosts: function() {
      const apiURL =
        process.env.VUE_APP_PRISMIC_API_URL +
        "ref=" +
        process.env.VUE_APP_PRISMIC_REF +
        '&q=[[at(document.type, "page")]]';

      axios
        .get(apiURL)
        .then(response => {
          const allPosts = response.data;
          // Update post information
          this.posts = allPosts.results;
          this.totalPages = allPosts.total_pages;
          this.currentPage = allPosts.page;
        })
        .catch(e => {
          this.errors.push(e);
        });
    }
  },
  mounted() {
    this.getPrismicPosts();
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import "../assets/scss/style.scss";
</style>
