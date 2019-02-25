<template>
<div class="add-todo">
  <form @submit.prevent="addTodo">
    <input name="title" v-model="title" v-validate="'min:5'" type="text" placeholder="Add Todo..."/>

    <transition name="alert-in" enter-active-class="animated flipInX" leave-active-class="animated flipOutX">
      <p class="alert" v-if="errors.has('title')">
        {{ errors.first("title") }}
      </p>
    </transition>
  </form>
</div>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    }
  },
  methods: {
    addTodo(e) {
      this.$validator.validateAll().then((result) => {
        if (!result) return

        const newTodo = { title: this.title, completed: false }

        this.title = ""

        this.$emit("add-todo", newTodo)
      })
    }
  }
}
</script>

<style scoped>
.add-todo {
  background: #fff;
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
