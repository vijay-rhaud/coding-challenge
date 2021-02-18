<template>
  <div id="app">
    <Header/>
    <Search/>
  </div>
</template>

<script>
import Header from './components/Header/Header.vue'
import Search from './components/Search/Search.vue'


export default {
  name: 'App',
  components: {
    Header,
    Search
  }
}
</script>

<style>
  @import './assets/styles/global.css';
</style>
