<script>
import SingleCard from "./SingleCard.vue"
import { store } from "../assets/data/store.js"
import axios from 'axios';
export default {

    name: "CardsList",
    components: {
        SingleCard,
    },
    data() {
        return {
            store
        }
    },
    methods: {        
        generateArchetypes() {
            axios.get(store.ARCHETYPES_URL)
                .then(response => {
                    store.archetypes = response.data
                    console.log(this.store.archetypes)
                })
        },
    },
    mounted(){
        this.generateArchetypes()
    }
}

</script>

<template>
    <section class="container">
        <div class="row row-cols-1 row-cols-md-3 row-cols-lg-6">

            <!-- cardItem -->
            <SingleCard :card="card" v-if="!store.loading"  v-for="card in store.cards"></SingleCard>

            <div v-else class="loader">
                Loading...
            </div>

        </div>
    </section>
</template>


<style lang="scss" scoped></style>