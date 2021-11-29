<template>
    <section>
        <input 
        v-model="Query"
        type="text" 
        placeholder="Search"
        @keyup.enter="$emit('userQuery',Query), clearinput()"
        >
        <button
            @click="$emit('userQuery',Query), clearinput()"
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

methods:{
    clearinput(){
        this.Query = '';
    }
}

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