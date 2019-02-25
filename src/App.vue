<template>
  <div id="app">
    <h1>TodoList</h1>

    <Todos />
  </div>
</template>

<script>
import Todos from "./components/Todos"

export default {
  name: "app",
  components: {
    Todos
  }
}
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Montserrat:400,700");
@import url("https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css");
@import url("https://cdn.jsdelivr.net/npm/animate.css@3.5.1");

body {
  background-color: #EEEEEE;
  font-family: 'Montserrat', sans-serif;
  display: grid;
  grid-template-rows: auto;
  justify-items: center;
  padding-top: 50px;
}

body, html {
  margin: 0;
  height: 100%;
}
#app {
  width: 50%;
  padding-bottom: 120px;
}
</style>
