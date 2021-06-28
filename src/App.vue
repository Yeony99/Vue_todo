<template>
  <div>
    <!-- TodoList component 렌더링 -->
    <TodoList v-bind:todos="todos"/>
    <AddTodo v-on:add-todo="addTodo"/>
  </div>
</template>

<script>
import TodoList from './components/TodoList'
import AddTodo from './components/AddTodo'

export default {
  name: 'app',
  components: {
    TodoList
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: '자바스크립트 공부',
          completed: false,
        },
        {
          id: 2,
          title: '빨래하기',
          completed: false,
        },
        {
          id: 3,
          title: '장보기',
          completed: false,
        },
        {
          id: 4,
          title: '청소기 돌리기',
          completed: false,
        },
        {
          i: 5,
          title: '은행 다녀오기',
          completed: false,
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
