<template>
  <div id="app">
    <Header @userQuery="getQuery" />
    <MainContent />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import MainContent from './components/MainContent.vue'


export default {
  name: 'App',
  components: {
    Header,
    MainContent,
  },

data(){
  return{
    Query:'',
  }
},

methods:{
  getQuery(dato){
    this.Query = dato;



  }
}
}

</script>

<style lang="scss">

</style>