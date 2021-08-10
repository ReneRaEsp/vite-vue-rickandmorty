<template>
  <section class="listCharacters">
      <FilterByStatus/>
      <div class="characters">
          <div
           v-for="character of characters" 
           :key="character.id" 
           class="characters_items">
              <CardCharacter :character="character"/>
          </div>
      </div>
  </section>
</template>

<script>
import {useStore} from 'vuex';
import {onMounted, computed} from 'vue';
import FilterByStatus from '../components/FilterByStatus.vue';
import CardCharacter from '../components/CardCharacter.vue';
export default {
    components:{
        CardCharacter, FilterByStatus
    },
    setup(){
        const store = useStore();
        const characters = computed(()=>{
            return store.state.charactersFilter;
        });
        onMounted(()=>{
            store.dispatch('getCharacters');
        });
        return {
            characters
        }
    },
};
</script>

<style scoped lang="sass">
    .listCharacters
       width: 100%
       .characters
           display: flex
           justify-content: center
           flex-direction: row
           flex-wrap: wrap 
           .characters_items
               margin: 1rem
</style>