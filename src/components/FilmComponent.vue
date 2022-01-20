<template>
  <div class="film-thumb">
    <h2>
      {{ title }}
    </h2>
    <h3>
      {{ titleOrig }}
    </h3>
    <h4>
      {{ origLang }}
    </h4>
    <h5>
      {{ vote }}
    </h5>
  </div>
</template>

<script>
export default {
  name: "FilmComponent",
  props: {
    title: String,
    titleOrig: String,
    origLang: String,
    vote: Number,
  },
};
</script>

<style></style>
