<template>
  <div>
    <form @click="addTodo">
      <label>
        <input type="text" name="title" placeholder="Add Todo">
      </label>
      <input type="submit" value="Add" class="btn">
    </form>
  </div>
</template>

<script>
// import uuid from 'uuid'
export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods:{
    addTodo(e){
      e.preventDefault();
      const newTodo = {
        // id: uuid.v4(),
        title:this.title,
        compete:false,
      }
      // send to parent
      this.$emit('add-todo',newTodo)
      this.title = '';
    }
  }
}
</script>

<style scoped>
form {
  display: flex;
}

input [type='text'] {
  flex: 10;
  padding: 5px;
}

input[type='submit'] {
  flex: 2;
}
</style>