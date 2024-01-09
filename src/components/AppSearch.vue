<script>
// importo store
import { store } from '../store';

export default {
    name: 'AppSearch',

    data(){
        return{
            store,
        }
    },
}

</script>

<template>
    <div class="container">
        <select class="selection" name="" id="" v-model="store.statusValue">
            <option value="" selected>: Select Archetype :</option>
            <option v-for="option in store.optionList" :key="option" value=" ">{{option.archetype_name}}</option>
        </select>
    </div>
</template>

<style lang="scss" scoped>

    .selection{
        margin: 10px 0;
    }
</style>