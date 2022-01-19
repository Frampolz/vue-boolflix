<template>
  <main>
    <FilmComponent />
  </main>
</template>

<script>
import FilmComponent from "./FilmComponent.vue";
import axios from "axios";
export default {
  components: {
    FilmComponent,
  },
  data() {
    return {
      //API PATH
      queryPath:
        "https://api.themoviedb.org/3/search/movie?api_key=7f52810091d935dae2806b7fc5d9448e",
      // query per cercare il contenito da inserire nel parametro
      filmSearch: "breaking bad",
      filmList: null,
    };
  },
  created() {
    this.film();
  },
  methods: {
    film() {
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
