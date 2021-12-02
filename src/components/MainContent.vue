<template>
    <div class="contenitore">

        <div class="main-placeholder ds-flex flex-column" v-show="filmList.length === 0 && seriesList.length === 0">
            <h2 class=" fs-2 mt-5 text-center">Scegli un titolo dal nostro catalogo e goditi lo spettacolo!</h2>
            <div class="ds-flex flex-grow-1 justify-content-around align-items-center"> 
                <img class=" flix-logo ms-5 mt-5" src="https://fontmeme.com/permalink/211202/bec1c906b74dd02dc222c398ed8c8df6.png" alt="FlixFlix">

                <div class="animation align-items-end">
                    <div class="one"></div>
                    <div class="two"></div>
                    <div class="three"></div>
                </div>
            </div>
        </div>

        <div class="ds-flex align-items-center mx-4 my-2"
            v-show="filmList.length > 0">
            <img src="https://upload.wikimedia.org/wikipedia/commons/f/ff/Netflix-new-icon.png" alt="logo">
            <h2 class="">Film</h2>
        </div>

        <section
                v-show="filmList.length > 0"
                class="film ds-flex p-2">
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
        <section 
        v-show="seriesList.length > 0"
        class="serie-tv ds-flex p-2">
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
    width:100%;
    height: calc(100vh - 120px);
    background-image: url('../assets/9wzdncrfj3tj-background.jpg');
    background-size:cover ;
    background-position: top;
    overflow-y:hidden;
    h2{
        color: #dc1a28;
    }
    .flix-logo{
        width: 500px;
        height:200px;
    }
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

.animation {
  display: flex;
} 

.animation div {
  margin: 10px;
  width: 50px;
  height: 50px;
  background-color: #dc1a28;
  border-radius: 50%;
  animation-duration: 0.8s;
  animation-iteration-count: infinite;
}

.one {
  animation-name: load-one;
}

@keyframes load-one {
  30% {
     transform: translateY(-50%);
  }
}

.two {
  animation-name: load-two;
}

@keyframes load-two {
  50% {
     transform: translateY(-50%);
  }
}

.three {
  animation-name: load-three;
}

@keyframes load-three {
  70% {
     transform: translateY(-50%);
  }
}

</style>