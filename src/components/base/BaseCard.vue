<template>
  <div
    class="
      rounded-xl
      shadow-md
      w-1/2
      bg-blue-900
      flex flex-row
      justify-start
      items-center
      px-4
      mt-2
    "
    :class="extraClass"
  >
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: ["extraClass"],
};
</script>

<style>
</style>