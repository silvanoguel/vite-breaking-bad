<script>
import AlienCard from "./AlienCard.vue";
import {store} from "../store";

export default {
    name: "AlienList",
    components: {
        AlienCard
    },
    data() {
        return {
            store
        }
    }
}

</script>

<template>
    <h2>lista alieni</h2>
    <div class="row row-cols-5">
        <div class="col" v-for="alien in store.aliens" :key="alien.id">
            <AlienCard :alien="alien"/>
        </div>
    </div>

</template>


<style scoped lang="scss">


</style>