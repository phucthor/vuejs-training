<script setup>
import { reactive, ref } from 'vue'

const object = reactive({
  count: 2,
  user: {
    age: 30
  },
  array: [1, 2, 3]
})

const change = () => {
  object.count++
  object.user.age++
  object.array.push(5)
}


</script>

<template>
  <div>
    <p>Count: {{ object.count }}</p>
    <p>Age: {{ object.user.age }}</p>
    <p>Array: {{ object.array }}</p>
    <button @click="change">Increase</button>
  </div>
</template>
