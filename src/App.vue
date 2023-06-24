<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppLoader from './components/AppLoader.vue';
import AppSearch from './components/AppSearch.vue';
import axios from "axios";
import { store } from "./store";

export default {
  components: {
    AppHeader,
    AppMain,
    AppLoader,
    AppSearch,
    emits: ["filter"]
  },
  data() {
    return {
      store
    }
  },
  mounted() {
    // store.loading = true;
    // axios.get(store.apiURL).then((resp) => {
    //   this.store.cards = resp.data.data;
    //   store.loading = false;
    // })
    this.getArchetype();
  },
  methods: {
    getArchetype() {
      this.store.loading = true;
      const params = {
        num: 20,
        offset: 0
      }
      if (this.store.selectedType) {
        params.archetype = this.store.selectedType;
      }
      axios.get(this.store.apiURL, {
        params
      }).then(resp => {
        this.store.cards = resp.data.data;
      }).catch(error => {
        console.log(error);
      }).finally(() => {
        this.store.loading = false;
      })
    },
    handleFilter() {
      this.getArchetype();
    }
  }
}
</script>

<template>
  <AppHeader />
  <AppSearch @filter="handleFilter"/>
  <AppMain />
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>