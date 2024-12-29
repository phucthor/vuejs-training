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
const editingTodo = ref(null)

const addTodo = () => {
  if (newTodo.value.trim() === '') return
  const todo = {
    id: todos.length + 1,
    text: newTodo.value
  }
  todos.push(todo)
  newTodo.value = ''
}

const deleteTodo = (id) => {
  const index = todos.findIndex(todo => todo.id === id)
  if (index !== -1) {
    todos.splice(index, 1)
  }
}

const editTodo = (todo) => {
  editingTodo.value = { ...todo }
}

const updateTodo = () => {
  if (editingTodo.value && editingTodo.value.text.trim() !== '') {
    const todo = todos.find(todo => todo.id === editingTodo.value.id)
    if (todo) {
      todo.text = editingTodo.value.text
      editingTodo.value = null
    }
  }
}

const cancelEdit = () => {
  editingTodo.value = null
}
</script>


<template>
  <div>
    <input
      type="text"
      v-model="newTodo"
      @keyup.enter="addTodo"
      placeholder="Add new todo"
    />
    <button @click="addTodo">Add Todo</button>

    <ul>
      <li v-for="todo in todos" :key="todo.id">
        <span v-if="editingTodo === null || editingTodo.id !== todo.id">
          {{ todo.id }}: {{ todo.text }}
          <button @click="editTodo(todo)">Edit</button>
          <button @click="deleteTodo(todo.id)">Delete</button>
        </span>
        <span v-else>
          <input
            type="text"
            v-model="editingTodo.text"
            @keyup.enter="updateTodo"
          />
          <button @click="updateTodo">Update</button>
          <button @click="cancelEdit">Cancel</button>
        </span>
      </li>
    </ul>
  </div>
</template>

