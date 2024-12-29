<script setup>
import { computed, ref, reactive } from 'vue'
const users = ref([
  {
    name: 'Tommy',
    age: 30,
    isActive: true,
  },
  {
    name: 'John',
    age: 50,
    isActive: false,
  },
  {
    name: 'Sou',
    age: 39,
    isActive: true,
  },
])
</script>

<template>
  <div>
    <ul>
      <template v-for="(user, index) in users" :key="user.name">
        <li v-if="!user.isActive">
          {{ user.name }}: {{ user.isActive ? 'Active' : 'Deactive' }} ({{ index }})
        </li>
      </template>
    </ul>
  </div>
</template>
