<template>
    <div class="contenitore">
        <h2 class="mx-4">Film</h2>
        <section class="film d-flex p-2">
                <Card
                v-for="element in filmList" :key="element.id"
                    :Poster="`https://image.tmdb.org/t/p/w500${element.poster_path}`"
                    :OriginalTitle="element.original_title"
                    :Title="element.title"
                    :Language="element.original_language"
                    :Vote="element.vote_average"
                    :Overview="element.overview"
                />
        </section>

        <h2 class="mx-4">Serie TV</h2>
        <section class="serie-tv d-flex p-2">
                <Card
                v-for="element in seriesList" :key="element.id"
                    :Poster="`https://image.tmdb.org/t/p/w500${element.poster_path}`"
                    :OriginalName="element.original_name"
                    :Name="element.name"
                    :Language="element.original_language"
                    :Vote="element.vote_average"
                    :Overview="element.overview"
                />
        </section>
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
.contenitore{
    overflow-x: auto ;
    padding-top: 120px;
    background-color: black;
    height: 100vh;
}
h2{
    color: white,
}

</style>