<script>
export default {
  props: {
    pic: String,
    name: String,
    type: String,
  },
};
</script>

<template>
  <img :src="pic" alt="" class="img-fluid" />
  <div class="text text-center pt-3">
    <h3 class="h5">{{ name }}</h3>
    <p class="text-dark pt-4">{{ type }}</p>
  </div>
</template>

<style lang="scss" scoped>
.text {
  background-color: #d48f38;
  height: 10rem;
  margin-bottom: 1rem;
  color: white;
}
.col {
  background-color: white;
}
</style>
