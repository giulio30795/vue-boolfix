<template>
  <div id="app">
    <Header @userQuery="getQuery" />
    <MainContent 
                :filmList="filmList"
                :seriesList="seriesList"
    />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import MainContent from './components/MainContent.vue'
import axios from 'axios'

export default {
    name: 'App',
    components: {
        Header,
        MainContent,
    },

data(){
    return{
        Query:'',
        filmList: [],
        seriesList: [],
    }
},

methods:{
    getQuery(dato){
        this.filmList = [],
        this.seriesList = [],
        this.Query = dato;

        if (dato !== ''){
        axios
            .get('https://api.themoviedb.org/3/search/movie',{
                params:{
                    api_key: '242cb2071d02c21e8ab48c9701678b9c',
                    query: `${dato}`
                },
            })
            .then((response) => {
                response.data.results.forEach(element => {
                this.filmList.push(element)
                });
            })
        axios
            .get('https://api.themoviedb.org/3/search/tv',{
                params:{
                    api_key: '242cb2071d02c21e8ab48c9701678b9c',
                    query: `${dato}`
                },
            })
            .then((response) => {
                response.data.results.forEach(element => {
                this.seriesList.push(element)
                });
            })

          }

        else {
            this.filmList = null
            this.seriesList = null
        }
        }
    
      }
  }

</script>

<style lang="scss">

</style>