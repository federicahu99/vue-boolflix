<template>
  <div>
    <h2>Movie:</h2>
    <div v-if="resultFilm === 0">
      Nessun contenuto trovato
    </div>
    <BaseCard :results="resultFilm" v-else/>
  </div>
</template>

<script>
import BaseCard from "./BaseCard.vue"

export default {
  name: "filmSection",
  components: { BaseCard }, 
  props: {
    resultFilm: Array,
  },
};
</script>

<style>
</style>