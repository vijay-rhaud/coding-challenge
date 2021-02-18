<template>
  <div id="app">
    <Header/>
    <Search/>
    <Film/>
  </div>
</template>

<script>
import Header from './components/Header/Header.vue'
import Search from './components/Search/Search.vue'
import Film from './components/Film/Film.vue'

export default {
  name: 'App',
  components: {
    Header,
    Search,
    Film
  }
}
</script>

<style>
  @import './assets/styles/global.css';
</style>
