<template>
    
    <div class="container-fluid">
        <div class="row">
            <div class="col-5 popular">
                <h3>I più popolari</h3>
            </div>
            <div class="col-7 search"> 
                <input type="text" placeholder=" CERCA IL TUO FILMPREFERITO..." v-model="searchString" @keyup.enter="$emit('search', searchString)">
                <i class="fas fa-search" @click="$emit('search', searchString)"></i>
            </div>

        </div>
        <div class="row art">
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
        Cards
    },
    props:{
        cards: Array,
        filteredMovies: Array
    }
}
</script>


<style lang="scss">
.art{
    height: 2500px;
    background-color:rgb(77, 75, 75)
}
h3{
    padding: 50px;
    color:white;
}
.row {
    background-color:rgb(77, 75, 75)
}
.search {
    padding: 50px;
} 
input {
    width: 500px;
    border-radius: 10px;
    padding: 10px;
}
.fa-search {
    color: white;
    margin-left: 20px;
    font-size: xx-large;
    cursor: pointer;
}
::placeholder {
  color: rgba(0, 0, 0, 0.8)
}
</style>