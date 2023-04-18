<script>
import AppHeader from "./components/AppHeader.vue";
import AlienList from "./components/AlienList.vue";
import axios from "axios";
import { store } from "./store";
import SearchBar from "./components/SearchBar.vue";

export default {
  components: {
    AppHeader,
    AlienList,
    SearchBar
  },
  data() {
    return {
      store
    }
  },
  mounted() {
    this.getAliens();
  },
  methods: {
    getAliens() {
      this.store.loading = true;
      const params = {};
      if (this.store.selectedStatus) {
        params.status = this.store.selectedStatus;
      }
      axios.get(this.store.apiURL, {
        params
      }).then(resp => {
        this.store.aliens = resp.data.data;
      }).catch(error => {
        console.log(error);
      }).finally(() => {
        this.store.loading = false;
      })
    },
    handleFilter() {
      this.getAliens();
    }
  }

}
</script>

<template>
  <AppHeader title="Yu-Gi-Oh Api" />
  <SearchBar @filter="handleFilter" />
  <AlienList />
</template>

<style lang="scss">
@use "./styles/general.scss";
</style>