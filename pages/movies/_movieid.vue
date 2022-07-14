<template>
  <Loading v-if="$fetchState.pending" />
  <div v-else class="container single-movie">
    <h1>{{ this.movie.title }}</h1>
  </div>
</template>

<script>
export default {
  name: 'single-movie',
  data() {
    return {
      movie: null,
    }
  },
  async fetch() {
    await this.getSingleMovie()
  },
  fetchDelay: 1000,
  methods: {
    async getSingleMovie() {
      const data = this.$axios.get(
        `https://api.themoviedb.org/3/movie/${this.$route.params.movieid}?api_key=37ed43a4f8eaa2abd75f9283692947bc&language=en-US`
      )
      const result = await data
      this.movie = result.data
      console.log(this.movie)
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
