<template>
  <div id="container">
    <div>
      <FilmSection id="films" :resultFilm="resultFilm" />
      <SeriesSection id="series" :resultSeries="resultSeries" />
    </div>
      <!-- <div v-else="!resultSeries && !resultFilm "> Comincia a cercare subito!</div> -->
  </div>
</template>

<script>
import FilmSection from "./FilmSection.vue";
import SeriesSection from "./SeriesSection.vue";

export default {
  name: "BaseMain",
  components: { FilmSection, SeriesSection },
  props: {
    resultSeries: Array,
    resultFilm: Array,
  },
};
</script>

<style scoped lang="scss">
#films {
  margin: 0px auto;
  color: white;
  width: 94vw;
}

#series{
  margin: 0px auto;
  color: white;
  width: 94vw;
}
</style>