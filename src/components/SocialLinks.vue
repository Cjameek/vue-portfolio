<template>
  <ul class="social__list" v-if="socialLinks && socialLinks.length">
    <li class="social__list-item" v-for="links in socialLinks" :key="links.uid">
      <a
        :href="links.data.social_link.url"
        target="_blank"
        rel="noopener nofollow"
      >
        <span :class="`icon-${links.uid}`"></span>
      </a>
    </li>
  </ul>
</template>

<script>
import axios from "axios";

export default {
  name: "SocialLinks",
  props: {
    parentClass: String
  },
  data() {
    return {
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
    }
  },
  mounted() {
    this.getPrismicSocial();
  }
};
</script>

<style></style>
