<template>
    <div class="contenitore">
        <h2 class="mx-2">Film</h2>
        <section class="film d-flex p-2">
                <Card
                v-for="element in filmList" :key="element.id"
                    :Poster="`https://image.tmdb.org/t/p/w500${element.poster_path}`"
                    :OriginalTitle="element.original_title"
                    :Title="element.title"
                    :Language="element.original_language"
                    :Vote="element.vote_average"
                />
        </section>

        <h2 class="mx-2">Serie TV</h2>
        <section class="serie-tv d-flex p-2">
                <Card
                v-for="element in seriesList" :key="element.id"
                    :Poster="`https://image.tmdb.org/t/p/w500${element.poster_path}`"
                    :OriginalName="element.original_name"
                    :Name="element.name"
                    :Language="element.original_language"
                    :Vote="element.vote_average"
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
}
h2{
    color: white,
}

</style>