<template>
  <label :class="{ 'bg-green-500' : isComplete }" @click.stop.prevent class="h-8 w-8 rounded-full border border-gray-400">
    <input type="radio" class="hidden">
  </label>
</template>

<script>
export default {
  props: {
    isComplete: Boolean
  }
}
</script>

<style>

</style>
