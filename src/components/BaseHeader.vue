<template>
  <div id="header">
    <h1>BOOfliX</h1>
    <BaseSearch @searched-text="searchText"/>
  </div>
</template>

<script>
import BaseSearch from './BaseSearch.vue'

export default {
  components:  {
    BaseSearch,
  },
   methods: {
    searchText(text) {
      this.$emit("searched-text", text);
    },
  },
}
</script>

<style scoped lang="scss">

  #header{
    background-color: #343434;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px;

    h1{
      background-color: #343434;
      color: red;
      font-size: 40px;
    }
    }


</style>