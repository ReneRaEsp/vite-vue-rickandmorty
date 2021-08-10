<template>
  <div class="search">
      <input 
      type="text"
      placeholder="Search by name"
      v-model="name"
      @keyup="filter()"
      >
  </div>
</template>

<script>
import {ref} from 'vue';
import {useStore} from 'vuex';
export default {
    setup() {
        const store = useStore();
        const name = ref('');

        const filter = () =>{
            store.dispatch('filterByName', name.value)
        };
        return {
            name, filter
        }
    }
}
</script>

<style scoped lang="sass">
    input
        display: flex
        align-self: center
        margin: auto
        margin-top: 16px
        border-radius: .3rem
        border: 0px solid rgba(30, 60, 70, .98)
        padding: .7rem
        width: 40vw
        font-size: 18px
</style>