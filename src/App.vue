<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

import { store } from "./data/store";

export default {
  data() {
    return {
      store,
    };
  },
  components: { AppHeader, AppMain },
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
