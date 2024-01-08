<script>
import SingleCharacter from './SingleCharacter.vue'
export default {
    name: 'CharactersList',

    components:{
        SingleCharacter,
    }
}
</script>

<template>
    <div class="container">
       <div class="bg">
            <div class="count">
                <h6>Found 20 cards</h6>
            </div>
            <div class="row">
                <div class="col-6 col-md-4 col-lg-3">
                    <SingleCharacter/>
                </div>
                <div class="col-6 col-md-4 col-lg-3">
                    <SingleCharacter/>
                </div>
                <div class="col-6 col-md-4 col-lg-3">
                    <SingleCharacter/>
                </div>
                <div class="col-6 col-md-4 col-lg-3">
                    <SingleCharacter/>
                </div>
                <div class="col-6 col-md-4 col-lg-3">
                    <SingleCharacter/>
                </div>
                <div class="col-6 col-md-4 col-lg-3">
                    <SingleCharacter/>
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