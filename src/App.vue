<template>
  <div id="app">
    <Header @filmSearch="getFilm($event)" />
    <Main />
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
      queryPath:
        "https://api.themoviedb.org/3/search/movie?api_key=7f52810091d935dae2806b7fc5d9448e",
      // query per cercare il contenito da inserire nel parametro
      filmSearch: "",
      filmList: [],
    };
  },
  methods: {
    getFilm(text) {
      //il dato inserito dentro l'input diventa il paramentro da inserire dentro la chiamata axios
      this.filmSearch = text;
      //chiamata axios
      axios
        .get(this.queryPath, {
          params: {
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
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
