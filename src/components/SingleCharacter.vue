<script>
export default{
    name: 'SingleCharacter',
    props: {
        info: Object
    }
}
</script>

<template>
    <div class="card text-center">
        <img :src= info.card_images[0].image_url :alt="info.name">
        <h4>{{info.name}}</h4>
        <div>{{info.race}}</div>
    </div>
</template>

<style lang="scss" scoped>

.card{
    background-color: orange;
    min-height: 470px;
    margin: 15px 20px;
    
}
</style>