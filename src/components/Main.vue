<template>
  <main class="main" :class="filmCall ? 'empty' : ''">
    <ul v-if="filmCall" class="d-flex">
      <li v-for="(film, index) in filmCall" :key="index">
        <FilmComponent
          :title="film.title || film.name"
          :titleOrig="film.original_title || film.original_name"
          :image="film.backdrop_path"
          :origLang="film.original_language"
          :vote="film.vote_average"
        />
      </li>
    </ul>
  </main>
</template>

<script>
import FilmComponent from "./FilmComponent.vue";

export default {
  name: "Main",
  components: {
    FilmComponent,
  },
  props: {
    filmCall: {
      type: Array,
      default() {
        return [];
      },
    },
    seriesCall: {
      type: Array,
      default() {
        return [];
      },
    },
  },
};
</script>

<style lang="scss">
@import "../../node_modules/flag-icon-css/css/flag-icons.css";
@import "../assets/scss/style.scss";
.main {
  overflow: auto;
  background-color: $bcMain;
  ul {
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    & li {
      margin: 1em;
      width: 342px;
      height: 192px;
    }
  }
}
.empty {
  height: calc(100vh - 70px);
}
</style>
