<template>
  <div
    class="
      container
      vh-100
      d-flex
      flex-column
      align-items-center
      justify-content-around
    "
  >
    <h1 class="text-secondary">Reaction Game</h1>
    <button class="btn btn-success">Start</button>
    <Block />
    <Results />
  </div>
</template>

<script>
import Block from "./components/Block.vue";
import Results from "./components/Results.vue";
export default {
  name: "App",
  components: {
    Block,
    Results,
  },
};
</script>

<style>
</style>
