<template>
  <div id="film-section">
    <h1>Movies:</h1>
    <BaseCard :results="resultFilm" />
  </div>
</template>

<script>
import BaseCard from "./BaseCard.vue";

export default {
  name: "filmSection",
  components: { BaseCard },
  props: {
    resultFilm: Array,
  },
};
</script>

<style scoped lang="scss">
h1 {
  color: red;
  margin-bottom: 35px;
}
#film-section {
  margin-bottom: 35px;

}
</style>