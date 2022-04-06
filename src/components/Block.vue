<template>
  <div
    type="button"
    @click="handleClick"
    class="bg-success text-light text-center rounded"
  >
    <p class="text-light p-5">Click inside me</p>
  </div>
</template>

<script>
export default {
  name: "Block",
  mounted() {
    console.log("Block has been mounted");
    this.startTime = Date.now();
  },
  data() {
    return {
      startTime: null,
      endTime: null,
    };
  },
  methods: {
    handleClick() {
      this.endTime = Date.now();
      this.$emit("onEnded", this.totalTime);
    },
  },
  computed: {
    totalTime() {
      return this.endTime - this.startTime;
    },
  },
};
</script>

<style>
</style>