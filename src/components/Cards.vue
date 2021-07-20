<template>
<div class="cards-container">
    <div class="cards-details"  @mouseover="hover=true" @mouseleave="hover=false">
        <div class="movie-poster">
            <img :src='generateImg' alt="poster">
        </div>
        <br>
        <div class="movie-details" v-if="hover" >
            <h4>
                {{ title }}
            </h4>
            <div class="original_launguage">
                Language: {{ original_language }}
                </div>  
            <div class="vote">
                Score: {{ vote_average}}
            </div> 
        </div>
    </div>
</div>
</template>


<script>
export default {
    name: 'Cards',
    props: {
        poster_path: String,
        title: String,
        original_title: String,
        original_language: String,
        vote_average: Number
    },
    computed:{
        generateImg(){
            return 'https://image.tmdb.org/t/p/w342' + this.poster_path
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
.cards-container{
    margin: 60px;
    position: relative;
    width: 320px;
    .movie-details{
        width: 200px;
        text-align: center;
        color:rgb(255, 255, 255);
        position: absolute;
        left: 100px;
        background-color: rgba(0, 0, 0, 0.8);
        box-shadow: 1px 1px 10px #aaa;
        padding: 10px;
    }
}
.movie-poster img {
    box-shadow: 1px 1px 50px #aaa;
}
</style>