<template>
  <div class="filter">
      <div @click="filter('')" class="item">
          All
      </div>
      <div @click="filter('Alive')" class="item">
          Alive
      </div>
      <div @click="filter('Dead')" class="item">
          Dead
      </div>
      <div @click="filter('unknown')" class="item">
          Unknown
      </div>
  </div>
</template>

<script>
import {useStore} from 'vuex';
export default {
    setup(){
        const store = useStore();
        const filter = ((status)=>{
            store.dispatch('filterByStatus', status)
        });
        return {
            filter
        };
    }
}
</script>

<style scoped lang="sass">
.filter
    display: flex
    width: 60vw
    margin: auto
    justify-content: space-evenly
    padding: 1rem
    background: rgba(20, 40, 40, .99)
    border-radius: .5rem
    .item
        padding-left: 20px
        padding-right: 20px
        padding-top: 10px
        padding-bottom: 10px
        background: rgb(10,60,100)
        color: white
        border-radius: .5rem
        &:hover
            cursor: pointer  
</style>