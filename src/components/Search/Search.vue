<template>
  <div class="search-bar-container">
    <input class="search-bar" v-model="searchQuery" placeholder="Search">
  </div>
</template>

<script>
export default {
  name: 'Search',
  data: function () {
    return {
      searchQuery: ''
    }
  }
}
</script>

<style scoped>
  @import './search.css';
</style>
