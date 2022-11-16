<template>
  <AppHeader title="Breking Bad Api"/>
  <main>
    <SearchBar />
    <ListCharacters :characters="ListCharacters"/>


  </main>
  
</template>

<script>
import { createDOMCompilerError } from '@vue/compiler-dom';
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import ListCharacters from './components/ListCharacters.vue';
import SearchBar from './components/Searchbar.vue';
export default {
      components: {
    AppHeader,
    SearchBar,
    ListCharacters
},
      data(){
        return {
          apiURL: 'https://www.breakingbadapi.com/api/characters',
          ListCharacters: [],
        }

      },
      methods: {
        getCharacters () {
                axios.get(this.apiURL).then(
                  (res ) => { 
                    this.ListCharacters = [...res.data]
                    console.log(this.ListCharacters)
                  },
                  
                )
        }

      },
      created () {
              this.getCharacters()
      }

}

</script>

<style lang="scss" scoped>



</style>
