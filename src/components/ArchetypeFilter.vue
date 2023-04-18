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
        archetype: Array
    }
}
</script>

<template>
    <select class="form-select-m rounded">
        <option value="" selected>Choose the archetype</option>
        
    </select>
</template>


<style lang="scss" scoped>

</style>