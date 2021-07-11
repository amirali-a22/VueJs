<template>
  <div v-bind:key="todo.id" v-for="todo in todos">
<!--        <h3>{{ todo.title }}</h3>-->

<!--        <todoItem v-bind:todo="todo"/>-->
        <todoItem v-bind:todo_item="todo" v-on:del-todo="$emit('del-todo',todo.id)" />
  </div>
</template>

<script>
import todoItem from "./todoItem";

export default {
  name: "todos",
  components: {todoItem},
  props: ['todos'],
}
</script>

<style scoped>

</style>