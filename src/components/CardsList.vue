<script>
import SingleCard from "SingleCard.vue"
    export default {

        name: "CardsList",
        components: {
            SingleCard
        },
        data() {
            return {
            store
            }
        }
    }        

</script>

<template>
    <section class="container">
        <div class="row row-cols-2 row-cols-md-3 row-cols-lg-6">

            <!-- cardItem -->
            <SingleCard :card="cards" v-for="card in store.cards" v-if="!store.loading"></SingleCard>

            <div class="loader" v-else>
                Loading...
            </div>

        </div>
    </section>
    
</template>


<style lang="scss" scoped>

</style>