<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import axios from "axios";
import { store } from "./data/store";

export default {
  data() {
    return {
      store,
      characters: [],
    };
  },
  components: { AppHeader, AppMain },

  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0")
      .then((response) => {
        store.characters = response.data.data;
      });
  },
};
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss">
body {
  background-color: #d48f38;
}
</style>
