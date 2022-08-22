<template>
  <div>
    <h2>Series:</h2>
    <div v-if="!resultSeries">
      Nessun contenuto trovato
    </div>
    <BaseCard :results="resultSeries" v-else/>
  </div>
</template>

<script>
import BaseCard from "./BaseCard.vue"
export default {
  name: "SeriesSection",
  components: { BaseCard },
  props: {
    resultSeries: Array,
  },

};
</script>

<style>
</style>