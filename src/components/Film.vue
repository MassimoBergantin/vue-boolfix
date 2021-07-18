<template>
    <div>
        <!-- {{title}}
        {{original_title}}
        {{original_language}}
        {{vote_averag}} -->
        <div class="title">{{title}}</div>
        <div class="original-title">{{original_title}}</div>
        <div class="vote-average">{{vote_average}}</div>
    </div>
</template>


<script>


export default {
    name: 'Film',
    props: {
        title: String,
        original_title: String,
        original_language: String,
        vote_average: String,
    }
}
</script>

<style lang="scss" scoped>

</style>