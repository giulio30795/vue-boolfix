<template>
    <div class="mx-1 card-container">

        <div class="img-container">
            <img v-if="!Poster.includes('null')" :src="Poster" alt="Title">

            <img v-else src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOEAAADhCAMAAAAJbSJIAAAAJFBMVEX4+vvb4OTx9PXl6ezf4+f19/nt8PLz9vfq7fDi5unc4eTs7/GWhAgrAAACGUlEQVR4nO3b23KqMBiAUQEtsn3/961OtydIJEUmaXCtS7n5v5FTEHc7AAAAAAAAAAAAAAAAAAAAAAAAzvr2PX3pgNf6oXnf8Icjjyv0XZxKh8R8rRTYNF+lU8IOqwU2zaF0TNBa++jFsXRM0H7Fwn3pmKAVA5umdEzQhxXuT/3h0B7/bbbwdrpfevopGRIVnq/dZOHT1WzZfUCpiJdu040uZovuVcskzIhNt2g/LVIw5zrcENuwmcLJHdeS3bREwKzrcJO1z+YKJ99h/IZ138bOtCUCZl2HSz8OL/fXkTVXgfnnxaaLnkt/FhDhxPzjJ7hNNzoQY4fhdYUUTMw+fYr7eEn3NPclYCgx+/QpwvPF9tHHNW4gMffwSR4HbK8fxtYWz4v4aWL26VM8F5z68/cXXTuNn1JMEosUzInVJAROEwvMP++dwEli9ulTvBU4Tsw8e5r3AkeJWSdPFaoZ+lNq4HNixrnTBQK73eSC+OpZ7+H+aC7X0L8SDhwlvn6Y3VVW2P3f0KYG1lbY3ba0iYGVFXYPm9q0wLoKu6dtbVJgVYXdaGOb9ItZRYXjwPMyMeUnwXoKp4FpqilcGlhN4eRhW7JaChd/hQpLU5hAYWEfVDgsfrl0qKRwDaVjghTWX7j9dxO3/37pmrtp6ZSIzb/nvdtNnm8v9Gff1f+A/1tcbPw/MwAAAAAAAAAAAAAAAAAAAAAAALl8A7+jEA62Pbx2AAAAAElFTkSuQmCC" alt="Title">
        </div>

        <div class="text-container">
            <ul class="list-unstyled">
                <li>
                    <h4>Titolo</h4>
                    {{OriginalTitle}}{{OriginalName}}
                </li>
                <li>
                    <h4>Titolo Originale</h4>
                    {{Title}}{{Name}}
                </li>
                <li>
                    <div>
                        <h4>Voto</h4>
                        <i v-for="(n, index) in Math.ceil(Vote / 2)" :key="`number-${index}`"
                        class="fas fa-star"></i>
                        <i v-for="(n, index) in 5 - Math.ceil(Vote / 2)" :key="`list-${index}`"
                        class="far fa-star"></i>
                    </div>
                </li>
                <li class="fs-6 overflow-auto">
                    {{Overview}}
                </li>
            </ul>
        </div>
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
    Overview: String,
    },

data(){
    return {
        lingua: [ "en", "it"],
    }
},
}
</script>

<style scoped lang="scss">

.card-container{
    position: relative;
    background-color: transparent;
            &:hover .text-container{
            display: block;
        h4{
            font-size: 1rem;
            color: #dc1a28;
            margin: 0;
        }
        li{
            font-size: 1.5rem;
        }
}
img {
    width: 300px;
    height: 450px;

}

.text-container{
    display: none;
    position: absolute;
    text-align: center;
    top: 0px;
    left: 0px;
    color: black;
    width: 100%;
    height:100%;
    overflow: hidden;
    background-color: rgba($color: #272626, $alpha: .5);
    }
}

</style>