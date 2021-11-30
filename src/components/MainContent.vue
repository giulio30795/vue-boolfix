<template>
    <div>
        <Card
        v-for="element in filmList && seriesList" :key="element.id"
        :OriginalTitle="element.original_title"
        :OriginalName="element.original_name"
        :Name="element.name"
        :Title="element.title"
        :Language="element.original_language"
        :Vote="element.vote_average"
        />

        <!-- <Card
        v-for="(element, index) in seriesList" :key="`list-${index}`"
        
        :OriginalName="element.original_name"
        
        :Name="element.name"
        :Language="element.original_language"
        :Vote="element.vote_average" -->
        
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