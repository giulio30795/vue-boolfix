<template>
    <ul>
        <li>{{OriginalTitle}}</li>
        <li>{{Title}}</li>
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
    Title: String,
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