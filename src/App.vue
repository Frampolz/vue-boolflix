<template>
  <div id="app">
    <Header @filmSearch="getSeries($event), getFilm($event)" />
    <Main :filmCall="searchList" />
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
      apiKey: "7f52810091d935dae2806b7fc5d9448e",
      language: "en-US",
      filmList: [],
      seriesList: [],
      searchList: [],
      enFlag: "gb",
      imgPlaceholder:
        "https://www.signfix.com.au/wp-content/uploads/2017/09/placeholder-600x400.png",
    };
  },
  created() {
    console.log(this.searchList);
  },
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
            api_key: this.apiKey,
            lang: this.language,
            //parametro preso dal dato inserito dall'utente
            query: this.filmSearch,
          },
        })
        .then((result) => {
          //dato restituito dalla chiamata axios
          this.filmList = result.data.results;
          this.filmList.forEach((element) => {
            this.searchList.push(element);
          });
          this.searchList.forEach((element) => {
            if (element.original_language.includes("en")) {
              element.original_language = this.enFlag;
            }
            if (element.vote_average > 5) {
              element.vote_average = element.vote_average / 2;
            }
            element.vote_average = Math.round(element.vote_average)
          });
        })
        .catch();
    },
    getSeries(text) {
      this.filmSearch = text;
      const category = "tv";
      axios
        .get(`${this.queryPath}${category}`, {
          params: {
            api_key: this.apiKey,
            lang: this.language,
            //parametro preso dal dato inserito dall'utente
            query: this.filmSearch,
          },
        })
        .then((result2) => {
          this.seriesList = result2.data.results;
          //console.log(this.seriesList);
          this.seriesList.forEach((element) => {
            this.searchList.push(element);
          });
          this.searchList.forEach((element) => {
            if (element.original_language.includes("en")) {
              element.original_language = this.enFlag;
            }
            if (element.vote_average > 5) {
              element.vote_average = element.vote_average / 2;
            }
            element.vote_average = Math.round(element.vote_average)
            /* if(element.backdrop_path.includes("null")) {
              
            } */
          });
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
