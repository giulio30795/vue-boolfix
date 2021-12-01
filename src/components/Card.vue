<template>
    <div class="mx-1">
        <ul class="list-unstyled" 
            v-if="OriginalTitle !== '' || OriginalName !== '' ">
            <img v-if="!Poster.includes('null')" :src="Poster" alt="Title">

            <img v-else src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAAJFBMVEX4+vvb4OTx9PXl6ezf4+f19/nt8PLz9vfq7fDi5unc4eTs7/GWhAgrAAACGUlEQVR4nO3b23KqMBiAUQEtsn3/961OtydIJEUmaXCtS7n5v5FTEHc7AAAAAAAAAAAAAAAAAAAAAAAAzvr2PX3pgNf6oXnf8Icjjyv0XZxKh8R8rRTYNF+lU8IOqwU2zaF0TNBa++jFsXRM0H7Fwn3pmKAVA5umdEzQhxXuT/3h0B7/bbbwdrpfevopGRIVnq/dZOHT1WzZfUCpiJdu040uZovuVcskzIhNt2g/LVIw5zrcENuwmcLJHdeS3bREwKzrcJO1z+YKJ99h/IZ138bOtCUCZl2HSz8OL/fXkTVXgfnnxaaLnkt/FhDhxPzjJ7hNNzoQY4fhdYUUTMw+fYr7eEn3NPclYCgx+/QpwvPF9tHHNW4gMffwSR4HbK8fxtYWz4v4aWL26VM8F5z68/cXXTuNn1JMEosUzInVJAROEwvMP++dwEli9ulTvBU4Tsw8e5r3AkeJWSdPFaoZ+lNq4HNixrnTBQK73eSC+OpZ7+H+aC7X0L8SDhwlvn6Y3VVW2P3f0KYG1lbY3ba0iYGVFXYPm9q0wLoKu6dtbVJgVYXdaGOb9ItZRYXjwPMyMeUnwXoKp4FpqilcGlhN4eRhW7JaChd/hQpLU5hAYWEfVDgsfrl0qKRwDaVjghTWX7j9dxO3/37pmrtp6ZSIzb/nvdtNnm8v9Gff1f+A/1tcbPw/MwAAAAAAAAAAAAAAAAAAAAAAALl8A7+jEA62Pbx2AAAAAElFTkSuQmCC" alt="Title">
            <li>{{OriginalTitle}}{{OriginalName}}</li>
            <li>{{Title}}{{Name}}</li>
            <li v-if="lingua.includes(Language)"><img :src="require(`../assets/${Language}.png`)" alt="Language"></li>
            <li v-else>{{Language}}</li>

            <li>
                <div>
                    <i v-for="(n, index) in Math.ceil(Vote / 2)" :key="`number-${index}`"
                    class="fas fa-star"></i>
                    <i v-for="(n, index) in 5 - Math.ceil(Vote / 2)" :key="`list-${index}`"
                    class="far fa-star"></i>
                </div>
            </li>
        </ul>
    </div>
    
</template>

<script>
export default {
name: 'Card',

props:{
    Poster: String,
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
ul{
    color:white;
}

img{
    width: 30px;
}

ul > img {
    width: 300px;
    height: 100%;
}



</style>