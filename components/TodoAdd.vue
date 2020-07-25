<template>
  <div class="input mb-10">
    <input v-model="name" placeholder="Todo" type="text" class="bg-white focus:outline-none focus:shadow-outline border border-gray-300 rounded-lg py-2 px-4 block w-full appearance-none leading-normal" @keyup.enter="handleAddTodo">
  </div>
</template>

<script>
export default {
  data () {
    return {
      name: ''
    }
  },
  methods: {
    handleAddTodo () {
      this.$emit('addTodo', { name: this.name, done: false })
      this.name = ''
    }
  }
}
</script>
