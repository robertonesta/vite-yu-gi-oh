<script>
import {store} from "../assets/data/store"
import CardsFound from "./CardsFound.vue"
import CardsList from "./CardsList.vue"
import ArchetypeFilter from "./ArchetypeFilter.vue"


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
        exFunction(){
            console.log("ciao")
           // "&archetype="+store.selectedArchetype
        }
    }
}
</script>

<template>
    <div class="sand-bg">
        <div class="container py-3">
            <ArchetypeFilter @changed="exFunction"></ArchetypeFilter>
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