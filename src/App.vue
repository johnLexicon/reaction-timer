<template>
  <div class="container d-flex flex-column align-items-center m-auto">
    <h1 class="text-secondary mb-3">Reaction Game</h1>
    <button
      class="btn btn-success mb-3"
      @click="handleStart"
      :disabled="hasStarted"
    >
      Start
    </button>
    <Block @onEnded="handleEnd" v-if="hasStarted" :delayTime="delayTime" />
    <Results :totalTime="totalTime" v-if="hasEnded" />
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
  data() {
    return {
      hasStarted: false,
      hasEnded: false,
      delayTime: null,
      totalTime: null,
    };
  },
  methods: {
    handleStart() {
      this.delayTime = 2000 + Math.random() * 5000;
      this.hasStarted = true;
      this.hasEnded = false;
    },
    handleEnd(totalTime) {
      this.totalTime = totalTime;
      this.hasEnded = true;
      this.hasStarted = false;
    },
  },
};
</script>

<style>
</style>
