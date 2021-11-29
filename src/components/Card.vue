<template>
      <ul>
          <li>{{OriginalTitle}}</li>
          <li>{{Title}}</li>
          <li>{{Language}}</li>
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
}
</script>

<style>

</style>