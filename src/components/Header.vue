<template>
    <header class="d-flex justify-content-between align-items-center">
        
        <div class="d-flex justify-content-center align-items-center">
            <img class="main-logo" src="https://fontmeme.com/permalink/211201/64bc1d45af49ec05ce492a388017c0ec.png" alt="FlixFlix">
            <ul class="d-flex m-0 list-unstyled">
                <li class="mx-4">Film</li>
                <li class="mx-4">Serie TV</li>
                <li class="mx-4">Documentari</li>
                <li class="mx-4">Cartoni Animati</li>
            </ul>
        </div>

        <div class="d-flex justify-content-end align-items-center">
            <i class="fas fa-bell mx-3"></i>
            <img class="logo-profilo" src="https://static.wikia.nocookie.net/925fa2de-087e-47f4-8aed-4f5487f0a78c/scale-to-width/755" alt="profile-logo">
            
            <input 
            v-model="Query"
            placeholder="Search"
            type="text"
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
    background-color: black;
    padding: 1rem;
    color: white;
    position: fixed;
    width: 100%;
    height: 120px;
    z-index:1;
    i{
        font-size: 1.5rem;
    }
    div{
        background-color: black;
    }
    li:hover{
        color:lightgray;
        transition: .2s
    }
    .main-logo{
        cursor: pointer;
        &:hover{
            transform: scale(1.03);
            transition: .3s;
        }
    }
}

li, i{
    cursor: pointer;
}

.logo-profilo{
    width: 40px;
    height: 40px;
    margin-right: 1rem;
    cursor: pointer;
}

input{
    color: white;
    background-color: black;
    border-style: none;
    border-bottom: 1px solid rgb(212, 209, 209);
        &:focus{
            border-bottom: 2px solid white;
            outline: none;
        &::placeholder{
            color:transparent;
        }
    }
}
button{
    background-color: black;
    margin-left: 1rem;
    color: white;
    border-radius: 20px;
    border-style: none;
    border: 2px solid white;
    padding: 5px;
    &:hover{
        outline: 1px solid white;
    }
}
</style>