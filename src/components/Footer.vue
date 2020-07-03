<template>
  <footer class="footer">
    <div class="footer__sub-footer">
      <div class="footer__copy">&copy; {{ getCurrentYear }} Cody Meek</div>
      <div class="footer__social">
        <!-- <ul v-if="socialLinks && socialLinks.length">
          <li :for="links in socialLinks" :key="links">
            {{ links }}
          </li>
        </ul> -->
      </div>
      <div class="footer__scroll">
        <button
          type="button"
          class="footer__scroll--button"
          @click="scrollBackToTop"
        >
          <span
            class="footer__scroll--button_icon icon-next"
            aria-hidden="true"
          ></span>
          <span class="footer__scroll--button_text sr-only">Back to Top</span>
        </button>
      </div>
    </div>
  </footer>
</template>

<script>
import axios from "axios";

export default {
  name: "Footer",
  data() {
    return {
      currentYear: "0",
      socialLinks: [],
      errors: []
    };
  },
  methods: {
    getPrismicSocial: function() {
      const apiURL =
        process.env.VUE_APP_PRISMIC_API_URL +
        "ref=" +
        process.env.VUE_APP_PRISMIC_REF +
        '&q=[[at(document.type, "social_links")]]';

      axios
        .get(apiURL)
        .then(response => {
          const allSocial = response.data;
          this.socialLinks = allSocial.results;
        })
        .catch(e => {
          this.errors.push(e);
        });
    },
    scrollBackToTop: function() {
      document.getElementById("app").scrollIntoView({
        behavior: "smooth",
        block: "start"
      });
    }
  },
  computed: {
    getCurrentYear: function() {
      return new Date().getFullYear();
    }
  },
  mounted() {
    this.getPrismicSocial();
  }
};
</script>

<style lang="scss">
@import "../assets/scss/layout/_footer.scss";
</style>
