<script>
export default {
    name: "SingleCard",
    props:{
        card: Object
    }
}
</script>

<template>
    <div class="col">
        <div class="SingleCard text-center">
            <img class="img-fluid" :src="card.card_images[0].image_url" alt="card.name">
            <div class="text">
                <h3>{{card.name}}</h3>
                <div class="archetype">{{card.archetype}}</div>
            </div>
        </div>

    </div>
</template>

<style lang="scss" scoped>

</style>