<script>
export default {
    name: "AppCard",
    props: {
        card: Object
    }
}
</script>

<template>
    <div class="card text-center">
        <img :src="card.card_images[0].image_url_small" alt="" srcset="">
        <h6 class="text-white text-uppercase mt-3">{{ card.name }}</h6>
        <p>{{ card.archetype }}</p>
    </div>
</template>

<style scoped lang="scss">
.card {
    height: 100%;
    background-color: rgb(212, 143, 56);
}
</style>