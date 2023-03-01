<script>
import axios from "axios";
import CharacterCard from "./CharacterCard.vue";

export default {
  data() {
    return {
      characters: [],
    };
  },

  components: {
    CharacterCard,
  },

  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0")
      .then((response) => {
        console.log(response.data.data);
        this.characters = response.data.data;
        // console.log(this.characters);
      });
  },
};
</script>

<template>
  <div class="card">
    <div class="top-text">
      <p class="fw-bold">Founds {{ characters.length }} cards</p>
    </div>
    <div class="row row-cols-5">
      <div class="col" v-for="character in characters">
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
