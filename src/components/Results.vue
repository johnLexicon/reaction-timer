<template>
  <div class="text-center">
    <p>Reaction time - {{ totalTime }} ms</p>
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
  props: {
    totalTime: {
      type: Number,
      required: true,
    },
  },
  computed: {
    gameResult() {
      if (this.$props.totalTime <= 200) return GameResult.THE_FLASH;
      else if (this.$props.totalTime <= 500) return GameResult.ALLRIGHT;
      else return GameResult.SNAIL;
    },
  },
};
</script>

<style>
</style>