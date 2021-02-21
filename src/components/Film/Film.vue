<template>
  <div>
    <div class="film-container">
      <div v-for="(film, index) in listOfFilms" :key="index">
        <div class="film-card">
          <div class="image-container">
            <img :src="film.imageUrl" class="image"/>
          </div>
          <div class="film-info">
            <h2 class="film-title">{{film.title}}</h2>
            <br/>
            <h3 class="film-director">{{film.director}}</h3>
            <br/>
            <p class="text">Release Date: {{film.releaseTimeStamp}}</p>
            <br/>
            <p class="text">Run Time: {{film.runtime}}</p>
            <br/>
            <p class="text">Rating: {{film.stars}}/5</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['listOfFilms']
}
</script>

<style scoped>
  @import './film.css';
</style>
