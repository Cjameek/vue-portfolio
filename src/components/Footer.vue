<template>
  <footer class="footer">
    <div class="footer__sub-footer">
      <div class="footer__copy">&copy; {{ getCurrentYear }} Cody Meek</div>
      <div class="footer__scroll">
        <button
          type="button"
          class="footer__scroll--button"
          @click="scrollBackToTop"
        >
          Back to Top
        </button>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
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
