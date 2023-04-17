<script>
export default {
    name: "AlienCard",
    props: {
        alien: Object
    }
}
</script>

<template>
    <main>
        <div class="container text-center">
            <img :src="alien.card_images[0].image_url_small" >
            <p> {{ alien.name }}</p>
            <p> {{ alien.archetype }}</p>
        </div>
    </main>

</template>


<style scoped lang="scss">

main {
    background-color: orange;
}

.container {
    width: 80%;
}

</style>