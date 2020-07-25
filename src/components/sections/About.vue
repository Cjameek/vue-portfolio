<template>
  <div class="about__container">
    <div class="about__content">
      <h2 class="about__subtitle">So, what <em>about</em> me...</h2>
      <span class="about__divider" aria-hidden="true"></span>
      <picture class="about__media">
        <img class="about__image" src="../../assets/img/bio.jpg" />
      </picture>
      <span class="about__bar" aria-hidden="true"></span>
    </div>
    <div class="about__intro">
      <p>
        Well, for starters, I'm a web developer based out of
        <strong>Warner Robins, GA</strong>
        currently operating as the senior web developer for
        <a
          href="https://www.mandr-group.com/"
          target="_blank"
          rel="nofollow noopener"
          ><strong>M&amp;R Marketing</strong></a
        >
        agency out of <strong>Macon, GA</strong>.
      </p>
      <p>
        Web development has been a passion for the past 10yrs, both as a
        professional and as a hobbyist. Who knew that trying to learn how to add
        a checkered background to my Myspace page would launch all this?
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "About",
  data() {
    return {
      content: ""
    };
  }
};
</script>

<style lang="scss">
.about {
  @media screen and (min-width: 900px) {
    padding-top: 145px;
  }
  &__container {
    display: flex;
    flex-direction: column;
    padding-top: 45px;

    @media screen and (min-width: 900px) {
      padding-top: 75px;
    }
  }

  &__content {
    position: relative;
    z-index: 1;
    display: flex;

    flex-direction: column;
    flex-wrap: wrap;
    align-items: center;

    @media screen and (min-width: 900px) {
      flex-direction: row;
      flex-wrap: nowrap;
      align-items: center;
      justify-content: space-between;
    }
  }

  &__title {
    transform: rotate(-15deg) scale(1) translateY(0);
    @media screen and (min-width: 900px) {
      transform: rotate(-15deg) scale(1.5) translateY(20px);
    }
  }

  &__subtitle {
    max-width: 450px;
    margin-top: 0;
    margin-bottom: 0;
    font-size: 70px;

    em {
      color: var(--color-blue);
    }

    @media screen and (max-width: 899px) {
      text-align: center;
    }
  }

  &__divider {
    position: relative;
    z-index: -1;
    background-color: var(--color-green);
    display: block;
    width: 100px;
    height: 3px;
    margin: 45px 0;

    @media screen and (min-width: 900px) {
      width: 3px;
      height: 100px;
      margin: 0;
    }
  }

  &__bar {
    background-color: var(--color-green);
    position: absolute;
    z-index: -1;
    bottom: 0;
    right: 0px;
    height: 100px;
    width: 500px;
    display: block;
    transform: skew(10deg, 10deg) translateX(60px);
    box-shadow: inset 10px 10px 0 0 var(--color-blue);
    opacity: 1;
  }

  &__image {
    width: 100%;
    max-width: 300px;
    border-radius: 100%;
  }

  &__intro {
    position: relative;
    z-index: 1;
    @media screen and (min-width: 900px) {
      max-width: 550px;
    }
  }
}
</style>
