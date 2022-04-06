<template>
  <div @click="handleClick" class="bg-success text-light text-center rounded">
    <p class="text-light p-5">Click inside me</p>
  </div>
</template>

<script>
export default {
  name: "Block",
  methods: {
    handleClick() {
      console.log("Clicked");
    },
  },
};
</script>

<style>
</style>