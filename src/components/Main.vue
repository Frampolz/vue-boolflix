<template>
  <main>
    <Search @filmSearch="getFilm($event)" />
    <ul>
      <li v-for="(film, index) in filmList" :key="index">
        <FilmComponent
          :filmTitle="film.title"
          :filmTitleOrig="film.original_title"
          :filmOrigLang="film.original_language"
          :filmVote="film.vote_average"
        />
      </li>
    </ul>
  </main>
</template>

<script>
import FilmComponent from "./FilmComponent.vue";
import Search from "./Search.vue";
import axios from "axios";
export default {
  components: {
    FilmComponent,
    Search,
  },
  data() {
    return {
      //API PATH
      queryPath:
        "https://api.themoviedb.org/3/search/movie?api_key=7f52810091d935dae2806b7fc5d9448e",
      // query per cercare il contenito da inserire nel parametro
      filmSearch: "",
      filmList: null,
    };
  },
  created() {},
  methods: {
    getFilm(text) {
      this.filmSearch = text;
      axios
        .get(this.queryPath, {
          params: {
            query: this.filmSearch,
          },
        })
        .then((result) => {
          this.filmList = result.data.results;
          console.log(this.filmList);
        })
        .catch();
    },
  },
};
</script>

<style></style>
