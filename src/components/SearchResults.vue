<template>
  <div>
    <h1>Search Results</h1>
    <h2>{{boom}}</h2>
  </div>
</template>

<script>
export default {
  name: 'SearchResults',
  data() {
    return {
      query: null,
    }
  },
  beforeMount() {
    this.query = this.$route.params.query
  }  
}
</script>

<style scoped>

</style>