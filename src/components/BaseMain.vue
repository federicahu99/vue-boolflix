<template>
  <div>
    <FilmSection id="films" :resultFilm="resultFilm"  />
    <SeriesSection id="series" :resultSeries="resultSeries"/>
  </div>
</template>

<script>
import FilmSection from "./FilmSection.vue";
import SeriesSection from "./SeriesSection.vue";

export default {
  name: 'BaseMain',
  components: { FilmSection, SeriesSection },
  props: {
    resultSeries: Array,
    resultFilm: Array,
  },
};
</script>

<style>
</style>