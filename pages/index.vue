<template>
  <div class="home">
    <Hero />
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      movies: [],
    }
  },
  methods: {
    async getMovies() {
      const data = this.axios.get(
        'https://api.themoviedb.org/3/movie/550?api_key=f1eeb07b7c050d06a34c73f15c027788'
      )
    }
  }
}
</script>
