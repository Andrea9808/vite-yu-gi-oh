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
        <img :src="info.card_images[0].image_url" :alt="info.card_sets[0].set_name">
        <h4>{{info.name}}</h4>
        <div>{{info.race}}</div>
    </div>
</template>

<style lang="scss" scoped>
</style>