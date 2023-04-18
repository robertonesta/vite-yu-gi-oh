<script>
import {store} from "../assets/data/store"
export default {
    name: "ArchetypeFilter",
    
    data () {   
        return {
            store
        }
    },
    props:{
        archetypes: Array
    }
}
</script>

<template>
    <select class="form-select-m rounded" @change="$emit('changed')">
        <option value="" selected>Choose the archetype</option>
        <option value="" v-for="archetype in store.archetypes">{{ archetype.archetype_name }}</option>
    </select>
</template>


<style lang="scss" scoped>

</style>