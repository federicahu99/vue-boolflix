<template>
  <div>
    <ul v-for="(result, i) in results" :key="i" class="card">
      <h1>{{ result.title || result.name }}</h1>
      <li>
        <h2>{{ result.original_title || result.original_name }}</h2>
      </li>
      <li>
        <img
          :src="getFlag(result)"
          :alt="result.original_title || result.original_name"
          v-if="gotFlag(result)"
        />
        <h2 v-else>{{ result.original_language }}</h2>
      </li>
      <li>
        <h2>{{ result.vote_average }}</h2>
      </li>
      <li>
        <img
          :src="getImage(result)"
          :alt="result.original_title || result.original_name"
        />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "BaseCard",
  props: { results: Array },
  data() {
    return {
      resultImg: "https://image.tmdb.org/t/p/w342",
    };
  },
  methods: {
    gotFlag(result) {
      const flag = ["it", "en"];
      return flag.includes(result.original_language);
    },
    getFlag(result) {
      return require(`../assets/img/${result.original_language}.png`);
    },
    getImage(result) {
      return require(`${this.resultImg}${result.poster_path}`);
    },
  },
}; 
</script>

<style>
</style>