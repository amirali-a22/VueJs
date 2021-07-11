<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo_item.complete}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      {{ todo_item.title }}
      <button @click="$emit('del-todo', todo_item.id)" class="del">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "todoItem",
  props: ['todo_item'],
  methods: {
    markComplete() {
      console.log(this.todo_item.complete)

      // eslint-disable-next-line vue/no-mutating-props
      this.todo_item.complete = !this.todo_item.complete;
    },

  }
}
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
}

.is-complete {
  text-decoration: line-through;
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
</style>