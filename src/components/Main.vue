<template>
    <div>
        <Film
        v-for="film in films" :key= 'film.id'
        :title="film.title"
        :original_title="film.original_title"
        :original_language="film.original_language"
        :vote_average="film.vote_average"
        />
    </div>
</template>

<script>

import Film from './Film.vue'

export default {
    name: 'Main',
    components: {
        Film
    },
    props: {
        films: Array
    }
}
</script>

<style lang="scss" scoped>

</style>