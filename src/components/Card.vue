<template>
    
    <ul v-if="OriginalTitle !== '' || OriginalName !== '' ">
        <li>{{OriginalTitle}}{{OriginalName}}</li>
        <li>{{Title}}{{Name}}</li>
        <li v-if="lingua.includes(Language)"><img :src="require(`../assets/${Language}.png`)" alt="Language"></li>
        <li v-else>{{Language}}</li>
        <li>{{Vote}}</li>
    </ul>
    
</template>

<script>
export default {
name: 'Card',
props:{
    OriginalTitle: String,
    OriginalName: String,
    Title: String,
    Name: String,
    Language: String,
    Vote: Number,
    },

data(){
    return {
        lingua: [ "en", "it"],
    }
},
}
</script>

<style scoped lang="scss">
img{
    width: 30px;
}

</style>