<template>
  <div class="todo-item" v-bind:class="{ 'is-complete': todo.completed }">
    <p>
      <input type="checkbox" v-on:change="markComplete" />
      {{ todo.title }}
      <button @click="$emit('del-todo', todo.id)" class="del">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px rgb(85, 4, 235) dotted;
}

.is-complete {
  text-decoration: line-through;
  color: rgb(0, 128, 0);
}

.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}

.del:hover {
  background: rgb(172, 27, 27);
}
</style>
