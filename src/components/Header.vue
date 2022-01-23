<template>
  <header class="header d-flex">
    <div class="logo">
      <a href="">
        <img
          src="https://image.tmdb.org/t/p/w342/wwemzKWzjKYJFfCeiB57q3r4Bcm.png"
          alt=""
        />
      </a>
    </div>
    <div class="search">
      <input
        @keyup.enter="sendSearch()"
        type="text"
        placeholder="cerca"
        v-model="searchFilm"
      />
      <i @click="sendSearch()" class="fas fa-search"></i>
    </div>
  </header>
</template>

<script>
export default {
  name: "Search",
  components: {},
  data() {
    return {
      searchFilm: "",
    };
  },
  created() {},
  methods: {
    sendSearch() {
      this.$emit("filmSearch", this.searchFilm);
      this.searchFilm = "";
    },
  },
};
</script>

<style lang="scss">
@import "../../node_modules/flag-icon-css/css/flag-icons.css";
@import "../assets/scss/style.scss";

.header {
  justify-content: space-between;
  padding: 1em 2em;
  background-color: #121212;
  .logo {
    img {
      width: 8em;
      background: $backHeader;
    }
  }
  .search {
    input {
      text-align: center;
      border-radius: 4px;
      &:focus {
        outline: none;
        border-color: red;
        box-shadow: 0 0 5px red;
      }
    }
    .fa-search {
      color: white;
      margin-left: 1em;
    }
  }
}
</style>
