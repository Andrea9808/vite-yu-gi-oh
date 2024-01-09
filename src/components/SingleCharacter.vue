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
      <img :src="info.card_images[0].image_url" :alt="info.name" >
      <div class="card-body">
        <h5 class="card-title">{{ info.name }}</h5>
        <div class="card-text">{{ info.archetype }}</div>
      </div>
    </div>
  </template>
<style lang="scss" scoped>

.card{
    background-color: rgb(218, 146, 13);
    min-height: 500px;
    margin: 15px 20px;

    img{
        width: 100%;
    }
}
</style>