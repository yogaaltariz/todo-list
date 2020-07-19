<template>
  <div>
    <div class="flex justify-between items-center mb-5">
      <span :class="{'line-through text-gray-500' : isComplete}" class="font-medium capitalize">{{ text }}</span>
      <radio :is-complete="isComplete" @click.native="changeStatus" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    text: String,
    isComplete: Boolean,
    index: Number
  },
  methods: {
    changeStatus () {
      this.$emit('changeStatus', { name: this.text, done: !this.isComplete })
    }
  }
}
</script>
