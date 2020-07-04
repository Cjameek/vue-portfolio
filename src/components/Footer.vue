<template>
  <footer class="footer">
    <div class="footer__sub-footer">
      <div class="footer__copy">&copy; {{ getCurrentYear }} Cody Meek</div>
      <div class="footer__social">
        <SocialLinks />
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
import SocialLinks from "./SocialLinks";
export default {
  name: "Footer",
  components: {
    SocialLinks
  },
  data() {
    return {
      currentYear: "0"
    };
  },
  methods: {
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
  }
};
</script>

<style lang="scss">
@import "../assets/scss/layout/_footer.scss";
</style>
