<template>
  <div class="film-thumb">
    <h2>
      {{ filmCallObj.title }}
    </h2>
    <h3>
      {{ filmCallObj.original_title }}
    </h3>
    <h4>
      {{ filmCallObj.original_language }}
    </h4>
    <h5>
      {{ filmCallObj.language }}
    </h5>
    <h6>
      {{ filmCallObj.vote_average }}
    </h6>
  </div>
</template>

<script>
export default {
  name: "FilmComponent",
  props: {
    filmCallObj: Object,
  },
};
</script>

<style></style>
