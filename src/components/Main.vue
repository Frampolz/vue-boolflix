<template>
  <main>
    <ul>
      <li>
        <FilmComponent
          v-for="(film, index) in filmCall"
          :key="index"
          :filmCallObj="film"
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
  },
};
</script>

<style></style>
