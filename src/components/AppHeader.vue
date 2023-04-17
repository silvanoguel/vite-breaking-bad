<script>
export default {
    name: "AppHeader",
    props: {
        title: String
    }
}
</script>

<template>
    <div class="container">
        <h2 class="text-left my-4">{{ title }}</h2>
    </div>

</template>

