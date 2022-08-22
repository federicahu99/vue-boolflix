<template>
  <div>
    <input
      type="text"
      placeholder="inserisci nome del film/serie"
      v-model.trim="text"
      @keyup.enter="searchText"
    />
    <button type="button" @click="searchText">Cerca</button>
  </div>
</template>

<script>

export default {
  name: "BaseSearch",

  data() {
    return {
      text: "",
    };
  },
  methods: {
    searchText() {
      this.$emit("searched-text", this.text);
    },
  },
};
</script>

<style scoped>

</style>
```