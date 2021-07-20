<template>
    
    
    <div class="container">
        <div class="row">
            <span class="title">I TITOLI DEL MOMENTO</span>
        </div>
        <div class="row ">
            <Cards class="cover col" 
            v-for=" cards in cards" :key="cards.id" 
            :poster_path="cards.poster_path" 
            :title="cards.title" 
            :original_title="cards.original_title" 
            :original_language="cards.original_language" 
            :vote_average="cards.vote_average" />
        </div>
    </div>

</template>


<script>
import Cards from "../components/Cards.vue";
export default {
    name: 'Main',
    components: {
        Cards,
    },
    props:{
        cards: Array,
        filteredMovies: Array,
    }   
}
</script>


<style lang="scss">
.container{
    max-width: 100%;
    height: 100vh;
    overflow-y:scroll;
    background-color:rgb(77, 75, 75)
}
.title {
    padding: 25px;
    font-size: 30px;
    color: white;
    text-align: center;
}
</style>