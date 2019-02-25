<template>
<div class="todos">
  <AddTodo v-on:add-todo="addTodo" />

  <ul>
    <transition-group name="list" enter-active-class="animated bounceInUp" leave-active-class="animated bounceOutDown">
      <li :key="index" v-for="(todo, index) in todos">
        <Todo :todo="todo" :index="index" v-on:remove-todo="removeTodo" v-on:toggle-todo="toggleTodo" />
      </li>
    </transition-group>
  </ul>

  <p>
    There's always more you can do!
  </p>
</div>
</template>

<script>
import AddTodo from "./AddTodo"
import Todo from "./Todo"

export default {
  name: "Todos",
  components: {
    AddTodo,
    Todo
  },
  data() {
    return {
      todos: [
        { "title": "Create new Vue.js project", "completed": true },
        { "title": "Add Todos Component", "completed": true },
        { "title": "Add Singular Todo Component", "completed": true },
        { "title": "Handle User Input", "completed": true },
        { "title": "Validate User Input", "completed": true },
        { "title": "Remove Todos", "completed": true },
        { "title": "Mark Todos as completed", "completed": false },
        { "title": "Add Style to the Project", "completed": false }
      ]
    }
  },
  methods: {
    addTodo(newTodo) {
      this.todos.push(newTodo)
    },
    removeTodo(index) {
      this.todos.splice(index, 1)
    },
    toggleTodo(index) {
      this.todos[index].completed = !this.todos[index].completed
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
  margin: 0;
  padding: 0;
  list-style-type: none;
}

p {
  text-align:center;
  padding: 30px 0;
  color: gray;
}

.todos {
  background: #fff;
  box-shadow: 0px 0px 40px lightgray;
}

</style>
