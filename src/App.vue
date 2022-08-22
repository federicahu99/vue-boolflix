<template>
  <div>
    <BaseHeader @searched-text="getResults" />
    <BaseMain :resultFilm="resultFilm" :resultSeries="resultSeries"/>
  </div>
</template>

<script>
import axios from "axios";
import BaseHeader from "./components/BaseHeader.vue";
import BaseMain from "./components/BaseMain.vue";


export default {
  name: "App",
  components: { BaseHeader, BaseMain},
  data() {
    return {
      resultFilm: [],
      resultSeries: [],
      baseUri: "https://api.themoviedb.org/3",
      api_key: "?api_key=50df027645bf57ccc3ef82b89c1c311b",
    };
  },
  methods: {
    getResults(searchingText){
      this.getMoviesResults(searchingText);
      this.getSeriesResults(searchingText);
    },
    getMoviesResults(searchingText) {
      axios
        .get(`${this.baseUri}/search/movie${this.api_key}&query=${searchingText}`)
        .then((res) => {
          this.resultFilm = res.data.results;
        })
        .catch((err) => {
          console.log(err);
        });
    },
    getSeriesResults(searchingText) {
      axios
        .get(`${this.baseUri}/search/tv${this.api_key}&query=${searchingText}`)
        .then((res) => {
          this.resultSeries = res.data.results;
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>

<style lang="scss">
</style>
