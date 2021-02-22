<template>
  <div class="search-bar-container">
    <input 
      class="search-bar" 
      v-model="userSearch" 
      placeholder="Search"
      @keyup="search()"
    >
  </div>
</template>

<script>
export default {
  name: 'Search',
  data: function () {
    return {
      userSearch: ''
    }
  },
  methods: {
    search() {
      this.$emit('user-search', this.userSearch);
    }
  }
}
</script>

<style scoped>
  @import './search.css';
</style>
