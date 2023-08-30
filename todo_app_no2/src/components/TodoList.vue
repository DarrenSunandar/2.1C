<template>
    <div class="todo-list">
      <h2>Todo List 📚</h2>
      <input v-model="newTodo" @keyup.enter="addTodo" placeholder="Add a new task..." class="todo-input">
      <button @click="addTodoManually">Add</button>
      <button @click="clearAll">Clear All</button>
      <ul>
        <todo-item v-for="(todo, index) in todos" :key="index" :todo="todo" @delete="deleteTodo(index)"></todo-item>
      </ul>
    </div>
  </template>
  
  
  
  
  <script>
import TodoItem from './TodoItem.vue';

export default {
  components: {
    TodoItem
  },
  data() {
    return {
      newTodo: '',
      todos: []
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim() !== '') {
        this.todos.push({ text: this.newTodo, completed: false });
        this.newTodo = '';
      }
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
    addTodoManually() {
      if (this.newTodo.trim() !== '') {
        this.todos.push({ text: this.newTodo, completed: false });
        this.newTodo = '';
      }
    },
    clearAll() {
      this.todos = [];
    }
  }
};
</script>

  

  
  <style scoped>
  .todo-list {
    background-color: grey;
    padding: 20px;
    box-sizing: border-box;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh; 
    width: 100vw; 
    margin: 0; 
    overflow: hidden; 
  }
  
    ul {
    list-style: none;
    margin: 0;
    padding: 0;
    max-height: calc(100vh - 120px); 
    overflow-y: auto;
  }
  
  
  button {
    background-color: green;
    border: none;
    color: white;
    padding: 8px 15px;
    border-radius: 3px;
    cursor: pointer;
    transition: background-color 0.2s;
    margin-left: 10px;
  }
  
  button:hover {
    background-color: white;;
  }
  
  
  @media (max-width: 600px) {
    .todo-list {
      max-width: 100%;
    }
  }
  </style>
  
  
  