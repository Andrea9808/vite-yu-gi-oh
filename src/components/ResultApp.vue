<script>
// importo store
import { store } from '../store';

export default {
    name: 'ResultApp',

    data(){
        return{
            store,
        }
    },

    computed:{
        resultNumber(){
            return store.characterList.length;
        }
    }
}

</script>

<template>
    <h6 v-if="resultNumber > 0">Found {{ resultNumber }} cards</h6>
    <h6 v-else>No result found. Try a different archetype</h6>
</template>

<style lang="scss" scoped>

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
</style>