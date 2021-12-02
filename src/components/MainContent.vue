<template>
    <div class="contenitore">

        <div v-show="filmList.length === 0 && seriesList.length === 0">
            <h2 class=" main-placeholder mt-5 text-center">Scegli un titolo dal nostro catalogo e goditi lo spettacolo!</h2>
        </div>



        <div class="ds-flex align-items-center mx-4 my-2"
            v-show="filmList.length > 0">
            <img src="https://upload.wikimedia.org/wikipedia/commons/f/ff/Netflix-new-icon.png" alt="logo">
            <h2 class="">Film</h2>
        </div>

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

        <div class="ds-flex align-items-center mx-4 my-2"
            v-show="seriesList.length > 0">
            <img src="https://upload.wikimedia.org/wikipedia/commons/f/ff/Netflix-new-icon.png" alt="logo">
            <h2 class="">Serie TV</h2>
        </div>
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

.main-placeholder{
    color: #dc1a28
}

.ds-flex{
    display: flex;
}

section{
    overflow-x:auto
}
.contenitore{
    overflow-y: auto ;
    padding-top: 120px;
    background-color: black;
    min-height: 100vh;
    img{
        width: 60px;
        height: 60px;
    }
}
h2{
    color: white,
}

</style>