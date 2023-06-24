<script>
import { store } from "../store";

export default {
    name: "AppSearch",
    emits: ["filter"],
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class="select-container">
        <div class="container-sm">
            <select class="select-type p-2 m-4" v-model="store.selectedType" @change="$emit('filter')">
                <option value="">All</option>
                <option value="Alien">Alien</option>
                <option value="Ally of justice">Ally of Justice</option>
                <option value="Ancient Gear">Ancient Gear</option>
            </select>
    </div>
    </div>
</template>

<style scoped lang="scss">
.select-container {
    background-color: rgb(212, 143, 56);
    .container-sm {
        width: 80%;
        select {
        border-radius: 5px;
        width: 160px;
        }
    }
}
</style>