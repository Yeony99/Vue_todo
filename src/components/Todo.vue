<template>
  <div v-bind:class="{'completed': todo.completed}">
      <p v-on:click="checkComplete">{{todo.title}}</p>
      <button @click="$emit('delete-todo', todo.id)">delete</button>
  </div>
</template>
<script>
export default {
  name: 'Todo',
  props: [
      "todo"
  ], 
  methods: {
    checkComplete() {
      this.todo.completed = !this.todo.completed
    }
  }
}
</script>
<style scoped>
  .completed {
    text-decoration: line-through; 
    /* 클릭시 text-decoration이 표시되도록. */
  }
</style>