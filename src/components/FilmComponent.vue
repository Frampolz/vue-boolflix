<template>
  <div class="film-thumb">
    <h2>
      {{ title }}
    </h2>
    <h3>
      {{ titleOrig }}
    </h3>
    <img :src="`http://image.tmdb.org/t/p/w300/${image}`" :alt="title" />
    <h4>
      <span :class="`flag-icon flag-icon-${origLang}`"></span>
    </h4>
    <h5>
      <i v-for="n in vote" :key="n" id="star" class="fas fa-star"></i>
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
    image: String,
  },
  created() {
   console.log(this.vote);
    
  }
};

</script>

<style lang="scss">
@import "../assets/scss/style.scss";
</style>
