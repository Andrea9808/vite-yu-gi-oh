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
    }
  },
  created(){
    this.getCharacters();
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
