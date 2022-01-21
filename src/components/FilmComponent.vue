<template>
  <div class="film-thumb">
    <span class="flag-icon flag-icon-en"></span>
    <h2>
      {{ title }}
    </h2>
    <h3>
      {{ titleOrig }}
    </h3>
    <h4>
      <span :class="`flag-icon flag-icon-${origLang}`"></span>
    </h4>
    <h5>
      {{ vote }}
    </h5>
  </div>
</template>

<script>
export default {
  name: "FilmComponent",
  props: {
    title: String,
    titleOrig: String,
    origLang: String,
    vote: Number,
  },
  computed: {
    changeflag() {
      if (this.origLang == "en") {
        return (this.origLang = "gb");
      }
    },
  },
};
</script>

<style lang="scss">
@import "../assets/scss/style.scss";
</style>
