<template>
  <div class="app-container">
    <h1 class="app-title">Rick and Morty Client</h1>
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

<style lang="sass">
  *
    padding: 0
    margin: 0

  body
    font-size: 16px
    font-family: monospace
    background-image: url('assets/img/fondo.jpg')
    background-attachment: fixed
    background-size: cover
    background-position: center
    background-repeat: no-repeat

  .app-container
    .app-title
      text-align: center
      padding: 1rem
      margin: auto
      margin-top: 1rem
      margin-bottom: 1rem
      border-radius: 1rem
      background: rgba(233, 233, 233, .82)
      width: 40%
</style>
