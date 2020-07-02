<template>
  <div class="hello">
    <Header />
    <h1>{{ msg }}</h1>
    <button type="button">Get content</button>
    <p>
      For a guide and recipes on how to configure / customize this project,<br />
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener"
        >vue-cli documentation</a
      >.
    </p>
    <h3>Ecosystem</h3>
    <ul>
      <li>
        <a href="https://router.vuejs.org" target="_blank" rel="noopener"
          >vue-router</a
        >
      </li>
      <li>
        <a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a>
      </li>
      <li>
        <a
          href="https://github.com/vuejs/vue-devtools#vue-devtools"
          target="_blank"
          rel="noopener"
          >vue-devtools</a
        >
      </li>
      <li>
        <a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener"
          >vue-loader</a
        >
      </li>
      <li>
        <a
          href="https://github.com/vuejs/awesome-vue"
          target="_blank"
          rel="noopener"
          >awesome-vue</a
        >
      </li>
    </ul>
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

html {
  font-family: sans-serif; /* 1 */
  -ms-text-size-adjust: 100%; /* 2 */
  -webkit-text-size-adjust: 100%; /* 2 */
}

body {
  margin: 0;
}

article,
aside,
details, /* 1 */
figcaption,
figure,
footer,
header,
main, /* 2 */
menu,
nav,
section,
summary {
  display: block;
}

audio,
canvas,
progress,
video {
  display: inline-block;
}

audio:not([controls]) {
  display: none;
  height: 0;
}

progress {
  vertical-align: baseline;
}

template, /* 1 */
[hidden] {
  display: none;
}

a {
  background-color: transparent;
}

a:active,
a:hover {
  outline-width: 0;
}

abbr[title] {
  border-bottom: none; /* 1 */
  text-decoration: underline; /* 2 */
  text-decoration: underline dotted; /* 2 */
}

b,
strong {
  font-weight: inherit;
}

b,
strong {
  font-weight: bolder;
}

dfn {
  font-style: italic;
}

h1 {
  font-size: 2em;
  margin: 0.67em 0;
}

mark {
  background-color: #ff0;
  color: #000;
}

small {
  font-size: 80%;
}

sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}

sub {
  bottom: -0.25em;
}

sup {
  top: -0.5em;
}

img {
  border-style: none;
}

svg:not(:root) {
  overflow: hidden;
}

code,
kbd,
pre,
samp {
  font-family: monospace, monospace; /* 1 */
  font-size: 1em; /* 2 */
}

figure {
  margin: 1em 40px;
}

hr {
  box-sizing: content-box; /* 1 */
  height: 0; /* 1 */
  overflow: visible; /* 2 */
}

button,
input,
select,
textarea {
  font: inherit;
}

optgroup {
  font-weight: bold;
}

button,
input,
select {
  overflow: visible;
}

button,
input,
select,
textarea {
  margin: 0;
}

button,
select {
  text-transform: none;
}

button,
[type="button"],
[type="reset"],
[type="submit"] {
  cursor: pointer;
}

[disabled] {
  cursor: default;
}

button,
html [type="button"], /* 1 */
[type="reset"],
[type="submit"] {
  -webkit-appearance: button; /* 2 */
}

button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}

button:-moz-focusring,
input:-moz-focusring {
  outline: 1px dotted ButtonText;
}

fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}

legend {
  box-sizing: border-box; /* 1 */
  color: inherit; /* 2 */
  display: table; /* 1 */
  max-width: 100%; /* 1 */
  padding: 0; /* 3 */
  white-space: normal; /* 1 */
}

textarea {
  overflow: auto;
}

[type="checkbox"],
[type="radio"] {
  box-sizing: border-box; /* 1 */
  padding: 0; /* 2 */
}

[type="number"]::-webkit-inner-spin-button,
[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
[type="search"] {
  -webkit-appearance: textfield;
}

[type="search"]::-webkit-search-cancel-button,
[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
</style>
