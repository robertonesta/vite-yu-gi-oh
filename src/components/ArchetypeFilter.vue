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
    <select class="form-select-m rounded" v-model="store.selectedArchetype" @change="$emit('generatoreCarte')">
        <option value="" selected>Choose the archetype</option>
        <option :value="archetype.archetype_name" v-for="archetype in store.archetypes">{{ archetype.archetype_name }}</option>
    </select>
</template>


<style lang="scss" scoped>

</style>