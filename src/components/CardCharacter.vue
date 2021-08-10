<template>
  <div class="character">
      <div class="characters">
        <h3>{{character.name}}</h3>
      </div> 
      <img class="image-character"
       :src="character.image" :alt="character.name">
       
  </div>
</template>

<script>
export default {
  props: ['character']
}
</script>

<style scoped lang="sass">
  .character
    display: flex
    justify-content: center
    flex-direction: column
    padding: 2rem
    background: rgba(20, 210, 40, .9)
    width: 20vw
    border-radius: 1rem
    margin-bottom: 0
    .image-character
      width: 15vw
      height: 15vw
      margin: auto
      border-radius: 50%
    .characters
      display: flex
      justify-content: center
      font-weight: bold
      color: white
      margin-bottom: 1.5rem


</style>