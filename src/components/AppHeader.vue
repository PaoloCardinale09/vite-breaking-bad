<script>
export default {
  data() {
    return {
      title: "Yu-Gi-Oh-Api",
    };
  },
};
</script>

<template>
  <header class="d-flex">
    <div>
      <img
        src="https://www.yugioh-card.com/en/wp-content/uploads/2020/09/TCG_logo_500x500.png"
        alt=""
      />
    </div>
    <h1>{{ title }}</h1>
  </header>
</template>

<style lang="scss" scoped>
header {
  height: 5rem;
  align-items: center;
  background-color: white;
}
img {
  height: 5rem;
}
</style>
