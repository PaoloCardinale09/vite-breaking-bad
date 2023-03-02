<script>
import CharacterCard from "./CharacterCard.vue";
import BaseSerch from "./BaseSerch.vue";
import { store } from "../data/store";
import axios from "axios";

export default {
  data() {
    return {
      store,
      endpoint: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0",
    };
  },

  components: {
    CharacterCard,
    BaseSerch,
  },

  methods: {
    fetch(url) {
      axios.get(url).then((response) => {
        store.characters = response.data.data;
      });
    },

    fetchFilteredCards(term) {
      // console.log(term);
      this.fetch(`${this.endpoint} &fname=${term}`);
    },
  },

  created() {
    this.fetch(this.endpoint);
  },
};
</script>

<template>
  <BaseSerch placeholder="Search Card" @on-search="fetchFilteredCards" />
  <div class="card">
    <div class="top-text">
      <p class="fw-bold">Founds {{ store.characters.length }} cards</p>
    </div>
    <div class="row row-cols-5">
      <div class="col" v-for="character in store.characters">
        <CharacterCard
          :pic="character.card_images[0].image_url"
          :name="character.name"
          :type="character.archetype"
        />
        <!-- <img
          :src="character.card_images[0].image_url"
          alt=""
          class="img-fluid"
        />
        <div class="text text-center pt-3">
          <h3 class="h4">{{ character.name }}</h3>
          <p class="text-dark pt-4">{{ character.archetype }}</p>
        </div> -->
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  background-color: white;
  padding: 3rem;
}

.top-text {
  background-color: black;
  color: white;
  height: 3rem;

  p {
    padding-left: 1rem;
    line-height: 3rem;
  }
}
</style>
