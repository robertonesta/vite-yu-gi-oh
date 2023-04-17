<script>
import CardsFound from "./CardsFound.vue"
import CardsList from "./CardsList.vue"

export default {
    name: "AppMain",
    components: {
        CardsFound,
        CardsList,
    }

}
</script>

<template>
    <div class="sand-bg">
        <div class="container py-3">
            <select class="form-select-m rounded" >
                <option selected>Choose the archetype</option>
                <option value="1">Alien</option>
            </select>
        </div>
        <div class="container py-3 bg-light">
            <CardsFound/>
            <CardsList/>
        </div>
    </div>   
</template>

<style lang="scss" scoped>
.sand-bg{
    background-color: #d48f38;
}

</style>