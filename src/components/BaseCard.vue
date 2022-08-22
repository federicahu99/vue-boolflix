<template>
  <div>
    <ul v-for="(result, i) in results" :key="i" class="card">
      <h1>{{ result.title || result.name }}</h1>
      <li>
        <h2>{{ result.original_title || result.original_name }}</h2>
      </li>
      <li>
        <img :src="getFlag(result)" :alt="result.original_language" v-if="gotFlag(result)" />
        <h2 v-else>{{ result.original_language }}</h2>
      </li>
      <li>
        <h2>{{ result.vote_average }}</h2>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "BaseCard",
  props: { results: Array },
  methods: {
    gotFlag(result) {
      const flag = ["it", "en"];
      return flag.includes(result.original_language);
    },
    getFlag(result) {
        console.log(result)
      return require(`../assets/img/${result.original_language}.png`);
    },
  },
};
</script>

<style>
</style>