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
        axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0").then((resp) => {
            this.store.aliens = resp.data.data;
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