
<template>
<div class="film-container">
    <div class="film-details">
        <div class="movie-poster" @mouseover="hover=true" @mouseleave="hover=false">
            <img :src='generateImg' alt="poster">
        </div>
        <div class="movie-details" v-if="hover" >
            <h5>{{ title }}</h5>
            <div class="original_launguage">Language: {{ original_language }}</div>  
            <div class="vote">Score: {{ vote_average}}</div> 
        </div>
    </div>
</div>
</template>


<script>


export default {
    name: 'Film',
    props: {
        poster_path: String,
        title: String,
        original_title: String,
        original_language: String,
        vote_average: Number
    },
    computed:{
        generateImg(){
            return 'https://image.tmdb.org/t/p/w342/' + this.poster_path
        }
    },
    data(){
        return{
            hover:false,
        }
    },
}        

</script>

<style lang="scss" scoped>
.film-container{
    margin:30px 25px;
    position: relative;
    max-width: 320px;
    .film-details{
        width: 340px;
        text-align: center;
        color:rgb(255, 255, 255);
        position: absolute;
        bottom:150px;
        background-color: rgba(96, 97, 99, 0.658);
    }
}
</style>