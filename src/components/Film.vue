
<template>
<div class="film-container">
    <div class="film-details">
        <img :src='generateImg' alt="poster">
        <h5>{{title}}</h5>
        <div class="original_launguage">{{original_language }}</div>  
        <div class="vote">{{vote_average}}</div>     
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
    }    
}
</script>

<style lang="scss" scoped>
</style>