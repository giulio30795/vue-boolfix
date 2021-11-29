<template>
  <section>
    <button @click="getFilm">search</button>
    <ul v-for="(element, index) in filmList" :key="`list-${index}`">
        <li>{{element.original_title}}</li>
        <li>{{element.overview}}</li>
        <li>{{element.title}}</li>
        <li>{{element.video}}</li>
    </ul>

  </section>
</template>

<script>
import axios from 'axios'
export default {
name: 'MainContent',

data(){
    return {
        filmList: []
    }
},

methods:{
    getFilm(){

    }
}

}

</script>

<style scoped lang="scss">


</style>