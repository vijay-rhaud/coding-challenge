<template>
  <div>
    <div class="film-container">
      <div v-for="(film, index) in listOfFilms" :key="index">
        <Film :film="film"/>
      </div>
    </div>
  </div>
</template>

<script>
  import Film from '../Film/Film.vue'

  export default {
    props: ['listOfFilms'],
    components: {
      Film
    }    
  }
</script>

<style scoped>
  @import './film-list.css';
</style>
