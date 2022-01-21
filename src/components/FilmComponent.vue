<template>
  <div class="film-thumb">
    <h2>
      {{ title }}
    </h2>
    <h3>
      {{ titleOrig }}
    </h3>
    <img :src="`http://image.tmdb.org/t/p/w500${image}`" alt="">
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
  data() {
    return {};
  },
  props: {
    title: String,
    titleOrig: String,
    origLang: String,
    vote: Number,
    image: String
  },
};
</script>

<style lang="scss">
@import "../assets/scss/style.scss";
</style>
