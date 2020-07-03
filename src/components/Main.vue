<template>
  <div class="hello">
    <Header />
    <h1>{{ msg }}</h1>
    <button type="button">Get content</button>

    <Footer />
  </div>
</template>

<script>
import Header from "./Header";
import Footer from "./Footer";
import axios from "axios";

export default {
  components: {
    Header,
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
        process.env.VUE_APP_PRISMIC_REF;

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

h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.button,
button[type="button"] {
  background: var(--color-red);
  border: 2px solid transparent;
  border-radius: 0.5rem;
  padding: 1.2rem 2.4rem;
  color: #fff;
  font-family: "Lato", sans-serif;
  font-weight: 700;
  letter-spacing: 1.12px;

  &.secondary {
    background: transparent;
    border-color: var(--color-red);
  }
}
</style>
