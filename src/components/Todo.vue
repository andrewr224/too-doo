<template>
<div class="todo">
  <li>
    <input type="checkbox" v-on:change="markComplete">
    {{ todo.todo }}
    <i class="fa fa-minus-circle" v-on:click="remove"></i>
  </li>
</div>
</template>

<script>
export default {
  name: "Todo",
  props: ["todo"],
  methods: {
    remove(e) {
      console.log("remove this item")
    },
    markComplete(e) {
      e.preventDefault()

      console.log("Mark this item as complete")
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
}

.completed {
  text-decoration: line-through;
}
</style>
