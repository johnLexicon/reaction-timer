<template>
  <div
    v-if="showBlock"
    type="button"
    @click="handleClick"
    class="bg-success text-light text-center rounded"
  >
    <p class="text-light p-5">Click Me</p>
  </div>
</template>

<script>
export default {
  name: "Block",
  props: {
    delayTime: {
      type: Number,
      required: true,
    },
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
    }, this.$props.delayTime);
  },
  data() {
    return {
      showBlock: false,
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
  watch: {
    showBlock(newValue, oldValue) {
      if (newValue === true) this.startTime = Date.now();
    },
  },
};
</script>

<style>
</style>