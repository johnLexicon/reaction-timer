<template>
  <div class="text-center">
    <p>Reaction time - {{ reactionTime }}</p>
    <h1 class="text-success">{{ gameResult }}</h1>
  </div>
</template>

<script>
class GameResult {
  static SNAIL = new GameResult("Snail");
  static ALLRIGHT = new GameResult("Allright");
  static THE_FLASH = new GameResult("The Flash");

  constructor(text) {
    this.text = text;
  }

  toString() {
    return this.text;
  }
}

export default {
  name: "Results",
  computed: {
    gameResult() {
      return GameResult.THE_FLASH;
    },
  },
};
</script>

<style>
</style>