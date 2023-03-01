<script>
import CharacterList from "./CharacterList.vue";
export default {
  data() {
    return {
      title: "hello world",
    };
  },
  components: { CharacterList },
};
</script>

<template>
  <main>
    <div class="container">
      <CharacterList />
    </div>
  </main>
</template>

<style lang="scss" scoped></style>
