<template>
  <div class="container">
    <div>
      <card>
        <div id="header" class="flex justify-between items-center mb-10">
          <div id="date" class="flex items-center">
            <span class="text-5xl mr-2 font-bold">12</span>
            <div class="flex flex-col">
              <span class="font-medium">JAN</span>
              <span>2016</span>
            </div>
          </div>
          <span class="uppercase font-medium">Tuesday</span>
        </div>
        <todo-add @addTodo="addTodo" />
        <div id="body" class="pb-10">
          <todo-item
            v-for="(todo,index) in todos"
            :key="index"
            :text="todo.name"
            :is-complete="todo.done"
            :index="index"
            @changeStatus="changeDone"
          />
        </div>
      </card>
      <floating-action-button class="mx-auto block -mt-10" />
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      todos: []
    }
  },
  methods: {
    addTodo (data) {
      this.todos.push(data)
    },
    changeDone (data) {
      const idx = this.todos.findIndex(function (todo) {
        return todo.name === data.name
      })

      this.$set(this.todos, idx, { name: data.name, done: data.done })
    }
  }
}
</script>
