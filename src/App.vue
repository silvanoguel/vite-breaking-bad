<script>
import AppHeader from "./components/AppHeader.vue";
import AlienList from "./components/AlienList.vue";
import axios from "axios";
import { store } from "./store";

export default {
  components: {
    AppHeader,
    AlienList
  },
  data() {
    return {
      store
    }
  },
  mounted() {
        store.loading = true;
        axios.get(store.apiURL).then((resp) => {
            this.store.aliens = resp.data.data;
            store.loading = false;
        })
    }
}
</script>

<template>
  <AppHeader title="Yu-Gi-Oh Api" />
  <AlienList />
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>