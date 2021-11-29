<template>
    <section>
        <input 
        v-model="Query"
        type="text" 
        placeholder="Search">
        
        <button
            @click="$emit('userQuery',Query)"
            >Search</button>
    </section>
</template>

<script>
export default {
name: 'Header',

data(){
    return {
        Query: '',
    }
},

}

</script>

<style scoped lang="scss">

section{
    padding: 1rem;
}

button{
    margin-left: 1rem;
}
</style>