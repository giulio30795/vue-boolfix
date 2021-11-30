<template>
    <div>
        <Card
        v-for="element in filmList" :key="element.id"
            :Poster="`https://image.tmdb.org/t/p/w500${element.poster_path}`"
            :OriginalTitle="element.original_title"
            :Title="element.title"
            :Language="element.original_language"
            :Vote="element.vote_average"
        />

        <Card
        v-for="element in seriesList" :key="element.id"
            :Poster="`https://image.tmdb.org/t/p/w500${element.poster_path}`"
            :OriginalName="element.original_name"
            :Name="element.name"
            :Language="element.original_language"
            :Vote="element.vote_average"
        />
    </div>
</template>

<script>
import Card from '@/components/Card.vue'
export default {
name: 'MainContent',

props:{
    filmList: Array,
    seriesList: Array,
},

components:{
    Card,
},

}

</script>

<style scoped lang="scss">


</style>