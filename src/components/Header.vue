<template>
    <header class="d-flex justify-content-between">
        
        <div class="d-flex justify-content-center align-items-center">
            <img src="https://fontmeme.com/permalink/211201/64bc1d45af49ec05ce492a388017c0ec.png" alt="FlixFlix">
            <ul class="d-flex list-unstyled">
                <li class="mx-4">Film</li>
                <li class="mx-4">Serie TV</li>
                <li class="mx-4">Documentari</li>
                <li class="mx-4">Cartoni Animati</li>
            </ul>
        </div>

        <div class="d-flex justify-content-end align-items-center">
            <img class="logo-profilo" src="https://static.wikia.nocookie.net/925fa2de-087e-47f4-8aed-4f5487f0a78c/scale-to-width/755" alt="profile-logo">
            
            <input 
            v-model="Query"
            type="text" 
            placeholder="Search"
            @keyup.enter="$emit('userQuery',Query), clearinput()"
            >
            <button
                @click="$emit('userQuery',Query), clearinput()">
                Search
            </button>
        </div>
    </header>
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

header{
    padding: 1rem;
}

.logo-profilo{
    width: 50px;
    margin-right: 1rem,
    
}

button{
    margin-left: 1rem;
}
</style>