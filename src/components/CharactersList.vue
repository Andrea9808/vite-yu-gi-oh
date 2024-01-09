<script>
import SingleCharacter from './SingleCharacter.vue'
import AppLoader from './AppLoader.vue'
import ResultApp from './ResultApp.vue'

//importo lo store
import { store } from '../store';

export default {
    name: 'CharactersList',

    components:{
        SingleCharacter,
        AppLoader,
        ResultApp,
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
                <ResultApp/>
            </div>
            <div v-if="!store.loading" class="row">
                <div v-for="card in store.characterList" :key="card" class="col-6 col-md-4 col-lg-3">
                    <SingleCharacter :info="card"/>
                </div>
            </div>

            <!-- LOADER -->
            <AppLoader v-else label="Yu-Gi-Oh"/>
       </div>
    </div>
</template>

<style lang="scss" scoped>


    .bg{
        background-color: white;
       

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