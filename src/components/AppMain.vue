<script>
import AppLoader from './AppLoader.vue';
import AppCard from './AppCard.vue';
import { store } from "../store";

export default {
    name: "AppMain",
    components: {
        AppLoader,
        AppCard
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
        <div class="container p-5">
            <div class="card-container">
                <h6 class="found text-white ps-3">Found 39 cards</h6>
                <AppLoader v-if="store.loading"/>
                <div class="row row-cols-5 row-gap-3">
                    <div class="col" v-for="element in store.cards">
                        <AppCard :card="element"/>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<style scoped lang="scss">
    main {
        background-color: rgb(212, 143, 56);
        .container {
            width: 80%;
            background-color: white;
            .card-container {
                background-color: white;
                .found {
                    width: 100%;
                    height: 50px;
                    background-color: #212529;
                    line-height: 50px;
                }
            }
        }
    }
</style>