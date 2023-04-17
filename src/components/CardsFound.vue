<script>
import {store} from "../assets/data/store"

export default {
    name: "CardsFound",
    data(){
        return{
            store
        }
    }
}
</script>

<template>
    <div class="dark-bg text-white p-2">
        <span v-if="store.cards"> Found {{store.cards.length}} cards</span>
    </div>
</template>



<style lang="scss" scoped>
.dark-bg{
    background-color: #212529;
}
</style>
