<template>
<div class="todos">
  <div class="holder">
    <ul>
      <transition-group name="list" enter-active-class="animated bounceInUp" leave-active-class="animated bounceOutDown">
        <li v-for="(data, index) in todos" :key="index">
          {{ data.todo }}
          <i class="fa fa-minus-circle" v-on:click="remove(index)"></i>
        </li>
      </transition-group>
    </ul>
  </div>
</div>
</template>

<script>
export default {
  name: "Todos",
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
  },
  methods: {
    remove(id) {
      console.log(`Implement a method to remove todo ${id}`)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css";
@import "https://cdn.jsdelivr.net/npm/animate.css@3.5.1";

.holder {
  background: #fff;
}

ul {
  margin: 0;
  padding: 0;
  list-style-type: none;
}

ul li {
  padding: 20px;
  font-size: 1.3em;
  background-color: #E0EDF4;
  border-left: 5px solid #3EB3F6;
  margin-bottom: 2px;
  color: #3E5252;
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
i {
  float: right;
  cursor: pointer;
}
</style>
