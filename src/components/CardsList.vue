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
        generateCards() {
            axios.get(store.API_URL)
                .then(response => {
                    store.cards = response.data.data
                    store.loading = false
                    console.log(this.store.cards)
                })
                .catch(err => {
                    console.log(err);
                    console.error(err.message);
                })
        },
        generateArchetypes() {
            axios.get(store.ARCHETYPES_URL)
                .then(response => {
                    store.archetypes = response.data
                    console.log(this.store.archetypes)
                })
        },
    },
    mounted(){
        this.generateCards(),
        this.generateArchetypes()
    }
}

</script>

<template>
    <section class="container">
        <div class="row row-cols-1 row-cols-md-3 row-cols-lg-6">

            <!-- cardItem -->
            <SingleCard :card="card" v-for="card in store.cards" v-if="!store.loading"></SingleCard>

            <div v-else class="loader">
                Loading...
            </div>

        </div>
    </section>
</template>


<style lang="scss" scoped></style>