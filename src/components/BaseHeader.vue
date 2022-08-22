<template>
  <div>
    <h1>Booflix</h1>
    <BaseSearch @searched-text='searchingText'/>
  </div>
</template>

<script>
import BaseSearch from './BaseSearch.vue'

export default {
  components:  {
    BaseSearch,
  },
  data () {
    return {
      searchingText: '',
    }
  },
   methods: {
    searchText() {
      this.$emit("searched-text", this.searchingText);
    },
  },
}
</script>

<style scoped>

</style>