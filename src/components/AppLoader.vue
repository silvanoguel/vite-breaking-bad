<script>
export default {
    name: "AppLoader"
}
</script>

<template>
    <div class="loader">
        <div class="text">Loading...</div>
    </div>
</template>

<style scoped lang="scss">

.loader {
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
}


.text {
    text-transform: uppercase;
    letter-spacing: 2px;
}
</style>