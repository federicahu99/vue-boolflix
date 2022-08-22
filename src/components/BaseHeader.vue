<template>
  <div>
    <h1>Booflix</h1>
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

<style scoped>

</style>