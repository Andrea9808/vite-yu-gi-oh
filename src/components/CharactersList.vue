<script>
import SingleCharacter from './SingleCharacter.vue'

//importo lo store
import { store } from '../store';

export default {
    name: 'CharactersList',

    components:{
        SingleCharacter,
    },

    data(){
    return{
      store,
    }
  },

}
</script>

<template>
    <div class="container">
       <div class="bg">
            <div class="count">
                <h6>Found 20 cards</h6>
            </div>
            <div class="row">
                <div v-for="card in store.characterList" :key="card" class="col-6 col-md-4 col-lg-3">
                    <SingleCharacter :info="card"/>
                </div>
            </div>
       </div>
    </div>
</template>

<style lang="scss" scoped>
    .bg{
        background-color: white;
        min-height: 500px;

        .count{
            background-color: black;
            min-height: 40px;
            color: white;
            display: flex;
            align-items: center;
            
            h6{
                margin: 0px 10px;
            }
        }
    }

</style>