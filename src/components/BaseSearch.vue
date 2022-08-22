<template>
  <div>
    <input
      type="text"
      placeholder="Inserisci nome del film/serie"
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

<style scoped lang="scss">
  input {
    background-color: aliceblue;
    border-color: grey;
    width: 250px;
    padding: 10px;
  }
  button {
    background-color: red;
    border-color: grey;
    width: 70px;
    padding: 10px;
    font-size: 18px;
  }
</style>
