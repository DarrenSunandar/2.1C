<template>
    <li class="todo-item" :class="{ 'completed': todo.completed }">
      <input type="checkbox" v-model="todo.completed">
      {{ todo.text }}
      <button @click="$emit('delete')">Delete</button>
    </li>
  </template>
  
  <script>
  export default {
    props: ['todo']
  };
  </script>
  
    <style scoped>
    
    li {
    list-style: none;
    }

    .completed {
    color: green;
    }
    </style>

  