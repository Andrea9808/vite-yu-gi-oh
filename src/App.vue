<script>

// AXIOS
import axios from 'axios';

import HeaderApp from './components/HeaderApp.vue'
import AppSearch from './components/AppSearch.vue'
import CharactersList from './components/CharactersList.vue'

//importo lo store
import { store } from './store';

export default{
  components:{
    HeaderApp,
    AppSearch,
    CharactersList,
  },

  data(){
    return{
      store,
    }
  },

  // richiesta personaggi/figurine
  methods: {
    getCharacters(){
      axios
      .get(store.apiURL)
      .then((res => {
        //console.log(res.data.data);
        store.characterList = res.data.data;
        store.loading = false;
      }))
      .catch((err)=>{
        console.log("Errori",err);
      })
    },

    // richiesta opzioni
    getOptions(){

      let myUrl = store.optionApiUrl;

      // se l'utente ha fatto una ricerca
      if (store.statusValue !== ""){
        myUrl += `${store.apiArchetypeParameter}=${store.statusValue}`
      }

      axios
      .get(store.optionApiUrl)
      .then((res => {
        //console.log(res.data);
        store.optionList = res.data;
      }))
      .catch((err)=>{
        console.log("Errori",err);
      })
    }
  },



  created(){
    this.getCharacters();
    this.getOptions();
  }
}
</script>

<template>
<HeaderApp/>

<main>
  <AppSearch/>
  <CharactersList/>
</main>
</template>

<style lang="scss">
  @use './styles/general.scss';
</style>
