<template>
    <div>
        <Card
        v-for="(element, index) in filmList" :key="`card-${index}`"
        :OriginalTitle="element.original_title"
        :OriginalName="element.original_name"
        :Title="element.title"
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
},

components:{
    Card,
},

}

</script>

<style scoped lang="scss">


</style>