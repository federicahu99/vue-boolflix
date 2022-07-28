<template>
  <div>
    <BaseHeader :films-list='films'/>
  </div>
</template>

<script>
import axios from "axios";
import BaseHeader from"./components/BaseHeader.vue"

export default {
  name: "App",
  components: { BaseHeader },
  data() {
    return {
      films: [],
      searchText: "",
      api: "https://api.themoviedb.org/search/movie?",
    };
  },
  method: {
    getAlbums() {
      const config= {
        params: {
          api_key :'50df027645bf57ccc3ef82b89c1c311b',
          query: this.searchText,
        }
      }
      axios
        .get(this.api, config)
        .then((res) => {
          this.films = res.data.response;
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
