<template>
  <div id="app">
    <Header @filmSearch="getSeries($event), getFilm($event)" />
    <Main 
    :filmCall="filmList"
    :seriesCall="seriesList"
     />
  </div>
</template>

<script>
import axios from "axios";
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data() {
    return {
      //API PATH
      queryPath: "https://api.themoviedb.org/3/search/",
      // query per cercare il contenito da inserire nel parametro
      filmSearch: "",
      api_key: "7f52810091d935dae2806b7fc5d9448e",
      language: "en-US",
      filmList: [],
      seriesList: [],
    };
  },
  created() {},
  methods: {
    getFilm(text) {
      //il dato inserito dentro l'input diventa il paramentro da inserire dentro la chiamata axios
      this.filmSearch = text;
      //categoria
      const category = "movie";
      //chiamata axios
      axios
        .get(`${this.queryPath}${category}`, {
          params: {
            api_key: this.api_key,
            lang: this.language,
            //parametro preso dal dato inserito dall'utente
            query: this.filmSearch,
          },
        })
        .then((result) => {
          //dato restituito dalla chiamata axios
          this.filmList = result.data.results;
          console.log(this.filmList);
        })
        .catch();
    },
    getSeries(text) {
      this.filmSearch = text;
      const category = "tv";
      axios
        .get(`${this.queryPath}${category}`, {
          params: {
            api_key: this.api_key,
            lang: this.language,
            //parametro preso dal dato inserito dall'utente
            query: this.filmSearch,
          },
        })
        .then((result2) => {
          this.seriesList = result2;
          console.log(this.seriesList.data.results);
        })
        .catch();
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
