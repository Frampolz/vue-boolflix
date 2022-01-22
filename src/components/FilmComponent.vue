<template>
  <div class="film-thumb">
    <div class="images">
      <img
        v-if="image == null"
        src="https://www.globalpharmatek.com/wp-content/uploads/2016/10/orionthemes-placeholder-image.jpg"
        alt=""
        class="placeholder-img"
      />
      <h2 v-if="image == null" class="placeholder-title">{{ title }} image</h2>
      <img :src="`http://image.tmdb.org/t/p/w342/${image}`" alt="" />
    </div>
    <div class="film-details">
      <h2>titolo: {{ title }}</h2>
      <h3>titolo originale: {{ titleOrig }}</h3>
      <h4>
        lingua originale:
        <span :class="`flag-icon flag-icon-${origLang}`"></span>
      </h4>
      <h5>
        <p v-if="vote < 1">
          voto: <i v-for="n in 5" :key="n" class="far fa-star"></i>
        </p>
        <p v-if="vote > 1">
          voto: <i v-for="n in vote" :key="n" id="star" class="fas fa-star"></i>
        </p>
      </h5>
    </div>
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
  created() {},
};
</script>

<style lang="scss">
@import "../assets/scss/style.scss";
.film-thumb {
  height: 100%;
  &:hover {
    border: 2px solid white;
    background-color: black;
  }
  &:hover .images {
    display: none;
  }
  &:hover .film-details {
    display: block;
  }
  .images {
    position: relative;
    .placeholder-img {
      width: 342px;
      height: 192px;
    }
    .placeholder-title {
      position: absolute;
      top: 1em;
      left: 50%;
      transform: translateX(-50%);
      font-size: 0.9em;
      color: rgb(92, 92, 92);
    }
  }

  .film-details {
    display: none;
    height: 100%;
    font-size: 0.7em;
    padding: 2em;
    color: white;
    &:hover {
      display: block;
    }
    h2,
    h3,
    h4,
    h5 {
      margin-bottom: 1em;
    }
    .fa-star {
      color: $starColor;
    }
  }
}
</style>
