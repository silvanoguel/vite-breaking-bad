<script>
export default {
    name: "AlienCard",
    props: {
        alien: Object
    }
}
</script>

<template>
    
    <div class="card text-center">
        <img :src="alien.card_images[0].image_url_small" >
        <p class="alien-name mt-2"> {{ alien.name }}</p>
        <p class="alien-type"> {{ alien.archetype }}</p>
    </div>


</template>


<style scoped lang="scss">

.card {
    background-color: #D48F38;
    color: white;
    height: 100%;
    border-radius: 0;
    border: none;
}

.alien-type {
    color: black;
} 

</style>