<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppLoader from './components/AppLoader.vue';
import axios from "axios";

export default {
  components: {
    AppHeader,
    AppMain,
    AppLoader
  },
  data() {
    return {

    }
  }
}
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>