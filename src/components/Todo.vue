<template>
<div class="todo" v-bind:class="{'completed':todo.completed}">
  <input type="checkbox" v-on:change="markComplete(index)" v-bind:checked="todo.completed">
  {{ todo.title }}
  <i class="fa fa-minus-circle" v-on:click="remove(index)"></i>
</div>
</template>

<script>
export default {
  name: "Todo",
  props: ["todo", "index"],
  methods: {
    remove(index) {
      this.$emit("remove-todo", index)
    },
    markComplete(index) {
      this.$emit("toggle-todo", index)
    }
  }
}
</script>

<style scoped>
.todo {
  padding: 20px;
  font-size: 1.3em;
  background-color: #E0EDF4;
  border-left: 5px solid #3EB3F6;
  margin-bottom: 2px;
  color: #3E5252;
}

i {
  float: right;
  cursor: pointer;
  color: #EC7063;
}

input {
  padding: 15px;
}

.completed {
  color: #D5D8DC;
}
</style>
