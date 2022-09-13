<template>
  <button
    class="
      p-4
      rounded-md
      mx-4
      text-lg
      font-semibold
      hover:underline hover:underline-offset-4
      transition
      duration-200
    "
    :class="mode"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "BaseButton",
  props: ["type", "mode"],
};
</script>

<style>
</style>