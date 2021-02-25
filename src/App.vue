<template>
  <div id="app">
    <Header/>
    <Search @user-search="storeSearch"/>
    <FilmList :listOfFilms="databaseSearch"/>
  </div>
</template>

<script>
  import Header from './components/Header/Header.vue'
  import Search from './components/Search/Search.vue'
  import FilmList from './components/FilmList/FilmList.vue'
  import Fuse from 'fuse.js'
  // import axios from 'axios'

export default {
  name: 'App',
  data () {
    return {
      listOfFilms: [
        {"title": "Electric Dreams", "director": "Steve Barron", "releaseTimeStamp": 459126000, "runtime": 112, "stars": 5, "imageUrl": "https://upload.wikimedia.org/wikipedia/en/e/ee/EDposter1984.jpg"}, 
        {"title": "Point Break", "director": "Kathryn Bigelow", "releaseTimeStamp": 676681200, "runtime": 122, "stars": 4, "imageUrl": "https://upload.wikimedia.org/wikipedia/en/7/7e/Pointbreaktheatrical.jpg"}, 
        {"title": "Die Hard", "director": "John McTiernan", "releaseTimeStamp": 602467200, "runtime": 132, "stars": 3, "imageUrl": "https://upload.wikimedia.org/wikipedia/en/7/7e/Die_hard.jpg"}, 
        {"title": "Godzilla", "director": "Ishirō Honda", "releaseTimeStamp": -504748800, "runtime": 96, "stars": 5, "imageUrl": "https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Gojira_1954_Japanese_poster.jpg/440px-Gojira_1954_Japanese_poster.jpg"}, 
        {"title": "Predator", "director": "John McTiernan", "releaseTimeStamp": 550450800, "runtime": 107, "stars": 5, "imageUrl": "https://upload.wikimedia.org/wikipedia/en/9/95/Predator_Movie.jpg"}, 
        {"title": "Aliens", "director": "James Cameron", "releaseTimeStamp": 522025200, "runtime": 137, "stars": 4, "imageUrl": "https://upload.wikimedia.org/wikipedia/en/f/fb/Aliens_poster.jpg"}, 
        {"title": "Terminator 2: Judgment Day", "director": "James Cameron", "releaseTimeStamp": 678495600, "runtime": 137, "stars": 3, "imageUrl": "https://upload.wikimedia.org/wikipedia/en/8/85/Terminator2poster.jpg"}
      ],
      searchValue: ''
    }
  },
  // mounted () {
  //   axios
  //     .get('https://coding-challenges.aptsolutions.net/api/movies.json')
  //     .then(response => (this.listOfFilms = response.data))
  //     .then(response => (console.log(response.data[0])))
  // },
  methods: {
    storeSearch(value) {
      this.searchValue = value;
    }
  },
  computed: {
    databaseSearch() {
      let searchQuery = this.searchValue;
      const fuse = new Fuse(this.listOfFilms, {
        keys: [
          'title',
          'director'
        ],
        isCaseSensitive: true,
        threshold: 0.5
      });
      const results = fuse.search(searchQuery);
      return searchQuery ? results.map(listOfFilms => listOfFilms.item) :this.listOfFilms;
    }
  },
  components: {
    Header,
    Search,
    FilmList
  }
}
</script>

<style>
  @import './assets/styles/global.css';
</style>