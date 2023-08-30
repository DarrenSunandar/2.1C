<template>
  <div id="app">
    <h1>Todo App</h1>
    <todo-list></todo-list>
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue';

export default {
  components: {
    TodoList
  }
};
</script>

<style>

#app {
  font-family: Arial, sans-serif;
  text-align: center;
  margin: 0 auto;
  padding: 20px;
  background-color: purple;
}

h1 {
  color: white;
  font-size: 80px;
}

.todo-list {
  color: #000000;
  max-width: 400px;
  margin: 0 auto;
  background-color: white;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 20px;
  box-sizing: border-box;
}

.todo-item {

  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 0;
  border-bottom: 1px solid #eee;
}

.completed {
  text-decoration: line-through;
  color: green;
}

input[type="checkbox"] {
  margin-right: 10px;
}

input[type="text"] {
  width: 100%;
  padding: 10px;
  border: none;
  border-radius: 3px;
  background-color: #000000;
  margin-bottom: 10px;
}

button {
  background-color: #ff6b6b;
  border: none;
  color: white;
  padding: 5px 10px;
  border-radius: 3px;
  cursor: pointer;
  transition: background-color 0.2s;
}

button:hover {
  background-color: #e54848;
}
</style>

