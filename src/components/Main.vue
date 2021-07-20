<template>
    
    <div class="container-fluid">
        <div class="row">
            <h3>I più popolari</h3>
            <Film class="cover col" 
            v-for=" film in film" :key="film.id" 
            :poster_path="film.poster_path" 
            :title="film.title" 
            :original_title="film.original_title" 
            :original_language="film.original_language" 
            :vote_average="film.vote_average" />
                
        </div>
    </div>

</template>


<script>

import Film from '../components/Film.vue'

export default {
    name: 'Main',
    components: {
        Film
    },
    props: {
        film: Array,
        filteredFilm: Array
    }
}
</script>


<style lang="scss">
.row{
    height: 1000px;
    overflow-y:scroll;
    background-color:rgb(77, 75, 75)
}
h3{
    padding-top:15px;
    color:white;
}
</style>