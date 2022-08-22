<template>
  <div id="series-section">
    <h1>Series:</h1>
    <BaseCard :results="resultSeries"/>
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

<style scoped lang="scss">

h1 {
color: red;
margin: 35px 0px; 
}

#series-section {
  margin-bottom: 35px;
  display:flex;
}

</style>