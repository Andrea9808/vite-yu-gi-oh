<script>

// AXIOS
import axios from 'axios';

import HeaderApp from './components/HeaderApp.vue'
import AppSearch from './components/AppSearch.vue'
import CharactersList from './components/CharactersList.vue'

//importo lo store
import { store } from './store';

export default {
  components: {
    HeaderApp,
    AppSearch,
    CharactersList,
  },

  data() {
    return {
      store,
    }
  },

  // richiesta personaggi/figurine
  methods: {
    getCharacters() {

      let myUrl = store.apiURL;


      // se l'utente ha fatto una ricerca
      if (store.statusValue !== "") {

        //console.log("Selected Archetype:", store.statusValue);
        myUrl += `archetype=${store.statusValue}`

      }
      //console.log('triggerato', store.statusValue);
      
      axios
        .get(myUrl)
        .then((res => {
          //console.log(res.data.data);
          store.characterList = res.data.data;
          store.loading = false;
        }))
        .catch((err) => {
          console.log("Errori", err);
        })
    },

    // richiesta opzioni
    getOptions() {
      axios
        .get(store.optionApiUrl)
        .then((res => {
          //console.log(res.data);
          store.optionList = res.data;
          console.log("Options:", store.optionList); 
        }))
        .catch((err) => {
          console.log("Errori", err);
        })
    }
  },



  created() {
    this.getCharacters();
    this.getOptions();
  }
}
</script>

<template>
  <HeaderApp />

  <main>
    <AppSearch @archetypeChanged="getCharacters" />
    <CharactersList />
  </main>
</template>

<style lang="scss">
@use './styles/general.scss';
</style>
