<script>
import AppLoader from './AppLoader.vue';
import { store } from "../store";
export default {
    name: "AppMain",
    components: {
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
        <div class="container-sm">
            <select class="select-type p-2 m-4" aria-label="Default select example">
                <option selected>Choose!</option>
                <option value="Alien">Alien</option>
                <option value="Noble Knight">Noble Knight</option>
                <option value="Melodious">Melodious</option>
                <option value="Archfiend">Archfiend</option>
            </select>
        </div>
        <div class="container p-5">
            <div class="card-container">
                <h6 class="found text-white ps-3">Found 39 cards</h6>
                <AppLoader v-if="store.loading"/>
            </div>
        </div>
    </main>
</template>

<style scoped lang="scss">
    main {
        // debug
        height: calc(100vh - 70px);
        background-color: rgb(212, 143, 56);
        .container-sm {
            width: 80%;
            select {
                border-radius: 5px;
                width: 160px;
            }
        }
        .container {
            width: 80%;
            // debug
            height: calc(100vh - 150px);
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