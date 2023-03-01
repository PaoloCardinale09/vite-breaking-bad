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
  <CharacterList />
</template>

<style lang="scss" scoped></style>
