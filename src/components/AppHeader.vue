<script>
export default {
    name: "AppHeader"
}
</script>

<template>
    <div class="header d-flex align-items-center">
        <div class="header-img d-flex align-items-center">
            <img src="../img/logo.jpg" alt="Logo">
        </div>
        <h1>Yu-Gi-Oh Api</h1>
    </div>
</template>

<style scoped lang="scss">
    .header {
        height: 70px;
        background-color: white;
        .header-img {
            height: 70px;
            margin: 0 30px;
            img {
                height: 25px;
            }
        }
    }
</style>