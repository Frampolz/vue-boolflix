<template>
  <main>
    <span class="flag-icon flag-icon-gb"></span>
    <ul>
      <li v-for="(film, index) in filmCall" :key="index">
        <FilmComponent
          :title="film.title || film.name"
          :titleOrig="film.original_title || film.original_name"
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
@import "../assets/scss/style.scss";
</style>
