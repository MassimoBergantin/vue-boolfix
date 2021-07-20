<template>
    <div class="">
        <div class="">
            <Film
            v-for="film in film" :key= "film.id"
            :poster_path="film.poster_path"
            :title="film.title"
            :original_title="film.original_title"
            :original_language="film.original_language"
            :vote_average="film.vote_average"
            />
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
.container-fluid{
    background-color:rgb(77, 75, 75)
}
.cover:hover{
    background-color: gray;
}
</style>