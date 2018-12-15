<template>
  <div>
    <h1>Search Results</h1>
    <div v-for="result in results" :key=result.id>
      <h1>{{ result.title }}</h1>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'SearchResults',
  data() {
    return {
      query: null,
      results: null
    }
  },
  beforeMount() {
    this.query = this.$route.params.query
    this.getResults(this.query)
  },
  methods: {
    getResults(q) {
      axios
        .get("https://api.dailysmarty.com/search", { params: { q } })
        .then(response => {
          console.log(response.data.posts)
        })
        .catch(error => {
          console.log(error)
        })
    }
  }
}
</script>

<style scoped>

</style>