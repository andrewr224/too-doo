<template>
<div class="todos holder">
  <ul :key="todo.id" v-for="todo in todos">
    <Todo :todo="todo" />
  </ul>
</div>
</template>

<script>
import Todo from "./Todo"

export default {
  name: "Todos",
  components: {
    Todo
  },
  data() {
    return {
      todos: [
        { "todo": "Create new Vue.js project" },
        { "todo": "Add Todos Component" },
        { "todo": "Add Singular Todo Component" },
        { "todo": "Handle User Input" },
        { "todo": "Validate User Input" },
        { "todo": "Remove Todos" },
        { "todo": "Add Style to the Project" }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.holder {
  background: #fff;
}

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

.container {
  box-shadow: 0px 0px 40px lightgray;
}

input {
  width: calc(100% - 40px);
  border: 0;
  padding: 20px;
  font-size: 1.3em;
  background-color: #323333;
  color: #687F7F;
}

.alert {
  background: #fdf2ce;
  font-weight: bold;
  display: inline-block;
  padding: 5px;
  margin-top: -20px;
}
</style>
