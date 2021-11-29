<template>
  <div id="app">
    <Header @userQuery="getQuery" />
    <MainContent :filmList="filmList"/>
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
  }
},

methods:{
  getQuery(dato){
    this.filmList = [],
    this.Query = dato;

    axios.get(`https://api.themoviedb.org/3/search/movie?api_key=242cb2071d02c21e8ab48c9701678b9c&query=${dato}`)
    .then((response) => {
          response.data.results.forEach(element => {
          this.filmList.push(element)
        });
        })

  }
}
}

</script>

<style lang="scss">

</style>