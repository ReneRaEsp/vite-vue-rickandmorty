<template>
  <div class="character">
      <img class="image-character"
       :src="character.image" :alt="character.name">
      <div class="characters">
        <h3 class="name">{{character.name}}</h3>
        <h5 class="status">Status: 
        <span 
        :class="
        [{alive:character.status == 'Alive'},
        {dead:character.status == 'Dead' },
        {unknown:character.status == 'unknown' }]" 
        class="char-stat">{{character.status}}
        </span></h5>
        <h5 class="species">Species: 
          <span
          :class="[{alien:character.species=='Alien'}
          ,{human:character.species=='Human'}]"
          >
          {{character.species}}
          </span>
          </h5>
        <h6 class="type" v-if="character.type != ''">({{character.type}})</h6>
        <h5 class="gender">Gender: 
          <span
          :class="[
           {male:character.gender=='Male'}
          ,{female:character.gender=='Female'}
          ,{unknown:character.gender=='unknown'}]"
          >
            {{character.gender}}
          </span>
        </h5>
        <h5 class="origin">Origin: 
          <span class="origin-name">{{character.origin.name}}</span></h5>    
        <h5 class="location">Location:
          <span class="location-name"> 
          {{character.location.name}}
          </span>
          </h5>
      </div> 
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
    width: 15vw
    border-radius: 1rem
    margin-bottom: 0
    .image-character
      width: 12vw
      height: 12vw
      margin: auto
      border-radius: 50%
    .characters
      display: flex
      justify-content: center
      flex-wrap: wrap
      font-weight: bold
      color: white
      margin-bottom: 1.5rem
      margin-top: 1.1rem
      border-radius: .5rem
      padding: .7rem
      background: rgba(200, 200, 200, .3)
      h3, h4, h5, h6
        padding-left: 2rem
        padding-right: 2rem
        text-align: center
        margin-top: .3rem
      .origin, .location
        padding-left: 0rem
        padding-right: 0rem
        width: 100%
        color: rgba(59, 59, 72, 1)
        .origin-name
          color: rgba(30, 20, 100, .9)
        .location-name
          color: rgba(70, 60, 170, .9)
      .status, .species, .gender
        color: rgba(59, 59, 52, 1)
      .type
        color: rgb(20, 20, 20)
       

//Conditionals classes for status 
.alive
  color: rgba(20, 100, 120, 1)
.dead
  color: rgba(220, 29, 60, 1)
.unknown
  color: black

//Conditionals classes for species
.alien
  color: rgba(4, 80, 7, 1)
.human
  color: rgba(120, 100, 24, 1)

//Conditionals classes for gender
.male
  color: rgb(40, 40, 150)
.female
  color: rgb(190, 30, 70)
</style>