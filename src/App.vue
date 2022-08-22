<template>
  <div>
    <BaseHeader @searched-text="getResults" />
    <BaseMain :film="resultFilm" :series="resultSeries"/>
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
      searchingText: "",
      resultFilm: [],
      resultSeries: [],
      baseUri: "https://api.themoviedb.org/3",
      api_key: "50df027645bf57ccc3ef82b89c1c311b",
      query: this.searchingText,
    };
  },
  method: {
    getResults(searchingText) {
      axios
        .get(`${this.baseUri}/search/movie?api_key=${this.api_key}&query=${searchingText}`)
        .then((res) => {
          this.resultFilm = res.data.response;
          this.resultSeries = res.data.response;
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
