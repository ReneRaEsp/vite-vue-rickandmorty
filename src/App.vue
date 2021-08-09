<template>
  <div>
    <h1>Rick and Morty Client</h1>
    <ListCharacters/>
  </div>
</template>

<script>
import ListCharacters from './components/ListCharacters.vue'
export default{
  name: 'App',
  components: {
    ListCharacters
  }
}
</script>

<style>

</style>
