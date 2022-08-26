<template>
  <div class="card">
    <ul v-for="(result, i) in results" :key="i">
      <li class="relative">
        <div class="absolute">
          <h2 id="result-title">{{ result.title || result.name }}</h2>
          <h3>{{ result.original_title || result.original_name }}</h3>
          <img
            :src="getFlag(result)"
            :alt="result.original_title || result.original_name"
            v-if="gotFlag(result)"
            class="flag"
          />
          <h3 v-else>{{ result.original_language }}</h3>
          <span>
            <i
              v-for="star in 5"
              :key="star"
              class="fa-star"
              :class="getStars(result) >= star ? 'fa-solid' : 'fa-regular'"
            ></i
          ></span>
          <span> ({{ getStars(result) }})</span>
        </div>
      </li>
      <li>
        <img
          :src="getImage(result)"
          :alt="result.original_title || result.original_name"
          class="result-img"
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
      if (!result.poster_path) {
        return "https://adriaticaindustriale.it/wp-content/uploads/2020/02/not-found.png";
      }
      return `${this.resultImg}${result.poster_path}`;
    },
    getStars(result) {
      return Math.ceil(result.vote_average / 2);
    },
  },
};
</script>

<style lang="scss" scoped>
.card {
  text-align: center;
  display: flex;
  flex-wrap: wrap;
  margin-bottom: 25px;
  justify-content: space-between;

  ul {
    flex-basis: 25%;
    height: 380px;

    .relative {
      position: relative;
     
    }
    .absolute {
      position: absolute;
      left: 20%;
      right: 20%;
      top: 45px;
      background-color: none;
    }
  }

  h2 {
    color: red;
    margin: 10px 0;
  }

  .flag {
    width: 40px;
  }

  .result-img {
    width: 95%;
    height: 350px;
  }
}
</style>