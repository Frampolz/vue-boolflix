<template>
  <div class="search">
    <input type="text" v-model="searchFilm" />
    <button @click="$emit('filmSearch', searchFilm)">search</button>
  </div>
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
