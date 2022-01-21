<template>
  <div class="film-thumb">
    <h2>
      {{ title }}
    </h2>
    <h3>
      {{ titleOrig }}
    </h3>
    <div class="images">
      <img
        v-if="image == null"
        src="https://www.globalpharmatek.com/wp-content/uploads/2016/10/orionthemes-placeholder-image.jpg"
        alt=""
        class="placeholder-img"
      />

      <img :src="`http://image.tmdb.org/t/p/w300/${image}`" :alt="title" />
    </div>

    <h4>
      <span :class="`flag-icon flag-icon-${origLang}`"></span>
    </h4>
    <h5>
      <p v-if="vote < 1">
        <i v-for="n in 5" :key="n" class="far fa-star"></i>
      </p>
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
  },
};
</script>

<style lang="scss">
@import "../assets/scss/style.scss";
.placeholder-img {
  width: 300px;
}
.fa-star {
  color: rgb(172, 172, 27);
}
</style>
