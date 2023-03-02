<script>
// import MyComponent from "./components/MyComponent.vue";

export default {
  data() {
    return {
      term: "",
    };
  },

  props: {
    placeholder: String,
  },

  emits: ["on-search"],

  methods: {
    clear() {
      this.term = "";
    },

    search() {
      this.$emit("on-search", this.term);
    },
  },

  // components: {
  //   MyComponent,
  // },
};
</script>

<template>
  <form @submit.prevent="" class="py-3">
    <div class="input-group">
      <input
        type="text"
        class="form-control"
        :placeholder="placeholder || 'Search...'"
        v-model="term"
        @keyup.enter="search"
      />
      <button class="btn btn-primary" type="button" @click="search">
        Search
      </button>
      <button class="btn btn-secondary" type="button" @click="clear">
        Reset
      </button>
    </div>
  </form>
</template>

<style lang="scss" scoped></style>
