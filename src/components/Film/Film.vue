<template>
    <div>
        <div class="film-card">
            <div class="image-container">
                <img :src="film.imageUrl" class="image"/>
            </div>
            <div class="film-info">
                <h2 class="film-title">{{film.title}}</h2>
                <br/>
                <h3 class="film-director">{{film.director}}</h3>
                <br/>
                <p class="text">Release Date: {{unixConverter}}</p>
                <br/>
                <p class="text">Run Time: {{film.runtime}}</p>
                <br/>
                <p class="text">Rating: {{film.stars}}/5</p>
                <br/>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['film'],
        computed: {
            unixConverter() {
                let unixTime = this.film.releaseTimeStamp;
                let convertedTime = new Date(unixTime * 1000);
                return (convertedTime.toDateString());
            }
        }
    }
</script>

<style scoped>
    @import './film.css';
</style>
