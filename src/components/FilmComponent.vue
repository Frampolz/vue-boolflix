<template>
  <div class="film-thumb">
    <h2>
      {{ filmTitle }}
    </h2>
    <h3>
      {{ filmTitleOrig }}
    </h3>
    <h4>
      {{ filmOrigLang }}
    </h4>
    <h5>
      {{ filmVote }}
    </h5>
  </div>
</template>

<script>
export default {
  name: "FilmComponent",
  props: {
    filmTitle: String,
    filmTitleOrig: String,
    filmOrigLang: String,
    filmVote: Number,
  },
  created() {},
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
