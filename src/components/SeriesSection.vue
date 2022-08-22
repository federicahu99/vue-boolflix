<template>
  <div>
    <h2>Series:</h2>
    <div v-if="resultFilm === 0">
      Nessun contenuto trovato
    </div>
    <BaseCard :results="resultSeries" v-else/>
  </div>
</template>

<script>
import BaseCard from "./BaseCard.vue"
export default {
  components: { BaseCard },
  name: "SeriesSection",
  props: {
    resultSeries: Array,
  },

};
</script>

<style>
</style>