<template>
  <main>
    <ul>
      <li v-for="(film, index) in filmCall" :key="index">
        <FilmComponent
         :title="film.title"
         :titleOrig="film.original_title"
         :origLang="film.original_language"
         :vote="film.vote_average"
          />
      </li>
    </ul>
    <ul>
      <li v-for="(series, index) in seriesCall" :key="index">
        <FilmComponent
         :title="series.name"
         :titleOrig="series.original_name"
         :origLang="series.original_language"
         :vote="series.vote_average"
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

<style></style>
