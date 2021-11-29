<template>
  <section>
    <ul v-for="(element, index) in filmList" :key="`list-${index}`">
        <li>{{element.original_title}}</li>
        <li>{{element.title}}</li>
        <li>{{element.original_language}}</li>
        <li>{{element.vote_average}}</li>
    </ul>

  </section>
</template>

<script>
export default {
name: 'MainContent',

props:{
    filmList: Array,
}
}

</script>

<style scoped lang="scss">


</style>