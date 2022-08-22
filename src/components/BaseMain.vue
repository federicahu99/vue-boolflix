<template>
  <div>
    <FilmSection id="films"/>
    <SeriesSection id="series"/>
  </div>
</template>

<script>
import FilmSection from "./FilmSection.vue";
import SeriesSection from "./SeriesSection.vue";

export default {
 components: { FilmSection, SeriesSection },
 props: {
        resultSeries: Array,
        resultFilms: Array
    }
}
</script>

<style>

</style>