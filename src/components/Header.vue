<template>
  <header>
    <input type="text" v-model="searchFilm" />
    <button @click="$emit('filmSearch', searchFilm)">search</button>
  </header>
</template>

<script>
export default {
  name: "Search",
  data() {
    return {
      searchFilm: "",
    };
  },
};
</script>

<style></style>
