<script>
import {store} from "../assets/data/store"
import CardsFound from "./CardsFound.vue"
import CardsList from "./CardsList.vue"
import ArchetypeFilter from "./ArchetypeFilter.vue"
import axios from "axios"


export default {
    name: "AppMain",
    components: {
        CardsFound,
        CardsList,
        ArchetypeFilter,
    },
    data(){
        return { 
            store
        }
    },
    methods:{
        generateCards() {
            if (this.store.selectedArchetype != ""){
                store.API_URL += `&archetype=${this.store.selectedArchetype}`
            }
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
        }
    },
    mounted(){
        this.generateCards()
    }
}
</script>

<template>
    <div class="sand-bg">
        <div class="container py-3">
            <ArchetypeFilter @generatoreCarte="generateCards()"></ArchetypeFilter>
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