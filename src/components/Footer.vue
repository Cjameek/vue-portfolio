<template>
  <footer class="footer">
    <div class="footer__sub-footer">
      <div class="footer__copy">
        &copy; {{ getCurrentYear }} Cody Meek
      </div>
      <div class="footer__scroll">
        <button 
        type="button" 
        class="footer__scroll--button" 
        @click="scrollBackToTop">
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
    }
  },
  methods: {
    scrollBackToTop: function(){
      document.getElementById('app').scrollIntoView({
        behavior: 'smooth',
        block: 'start'
      });
    }
  },
  computed: {
    getCurrentYear: function() {
      return new Date().getFullYear();
    }
  }
}
</script>

<style lang="scss">
.footer {
  background: var(--color-dark);
  position: relative;
  margin-top: 7.4rem;
  padding: 3rem;
  color: #fff;

  &:before {
    content: '';
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1440 320'%3E%3Cpath fill='%23040f16' fill-opacity='1' d='M0,160L1440,224L1440,320L0,320Z'%3E%3C/path%3E%3C/svg%3E");
    background-position: bottom;
    background-repeat: no-repeat;
    background-size: cover;
    position: absolute;
    z-index: -1;
    top: -70px;
    left: 0;
    right: 0;
    width: 100%;
    height: 150px;
  }

  &__sub-footer {
    display: flex;

    > * {
      flex: 1 0 33.33%;
    }
  }
}
</style>