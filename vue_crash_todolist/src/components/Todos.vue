<template>
  <div>
      <!-- a directive like v-for and v-bind is some special token in the markup that tells the library to do something to a DOM element -->
    <div v-for="todo in todos" v-bind:key="todo.id">
      <h3>{{ todo.title }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "Todos",
  props: ["todos"],
};
</script>

<style scoped>
</style>