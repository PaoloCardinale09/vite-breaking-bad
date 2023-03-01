<script>
import axios from "axios";

export default {
  data() {
    return {
      characters: [],
    };
  },

  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=1&offset=0")
      .then((response) => {
        console.log(response);
        this.characters = response.data.data[0].archetype;
      });
  },
};
</script>

<template>
  <div>ciao</div>
</template>

<style lang="scss" scoped></style>
