<script setup>
import { computed, ref, reactive } from 'vue'
const todos = reactive([
  {
    id: 1,
    text: 'Learn Looker'
  },
  {
    id: 2,
    text: 'Learn how to build a basic app'
  },
  
])

const newTodo = ref('')

const addTodo = () => {
  if(newTodo.value.trim() === '') return
  const todo = {
    id: todos.length + 1,
    text: newTodo.value
  }
  todos.push(todo)
  newTodo.value = ''
}
</script>

<template>
  <div>
    <input type="text" v-model="newTodo" @keyup.enter="addTodo"/>
    <button @click="addTodo">Add Todo</button>
    <ul>
        <li v-for="todo in todos" :key="todo.id">
          {{ todo.id }}: {{ todo.text}}
        </li>
    </ul>
  </div>
</template>
