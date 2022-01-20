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
/* Milestone 1:
Creare un layout base con una searchbar (una input e un button) in cui possiamo scrivere completamente o parzialmente il nome di un film. Possiamo, cliccando il  bottone, cercare sull’API tutti i film che contengono ciò che ha scritto l’utente.
Vogliamo dopo la risposta dell’API visualizzare a schermo i seguenti valori per ogni film trovato: 
Titolo
Titolo Originale
Lingua
Voto */
</script>

<style></style>
