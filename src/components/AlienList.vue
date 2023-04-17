<script>
import AlienCard from "./AlienCard.vue";
import AppLoader from "./AppLoader.vue";
import {store} from "../store";

export default {
    name: "AlienList",
    components: {
        AlienCard,
        AppLoader
    },
    data() {
        return {
            store
        }
    }
}

</script>

<template>
    <main>
        <div class="container">
            <AppLoader v-if="store.loading" />
            <div class="row row-cols-5 g-3" v-else>
                <div class="col" v-for="alien in store.aliens" :key="alien.id">
                    <AlienCard :alien="alien"/>
                </div> 
            </div>   
        </div>
    </main>


</template>


<style scoped lang="scss">

main {
    background-color: #D48F38;
}

.container {
    width: 80%;
    padding: 30px;
    background-color: white;
}

</style>