<template>
  <section class="listCharacters">
      <div class="characters">
          <div v-for="character of characters" :key="character.id" class="characters_items">
              <h2>Characters</h2>
              {{character.name}}
          </div>
      </div>
  </section>
</template>

<script>
import {useStore} from 'vuex';
import {onMounted, computed} from 'vue';
export default {
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

<style>

</style>