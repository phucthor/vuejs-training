<script setup>
import { reactive, ref, watch } from 'vue'

const x = ref(0)
const y = ref(0)

const user = reactive({
  age: 30
})

watch(()=> x.value + y.value,
(sum) => {
  // console.log(`Sum of x and y is ${sum}`)
})

watch([x, () => y.value + 1], ([newX, newY]) => {
  console.log(`x is ${newX}, y is ${newY}`)
})

watch(user.age, (newAge) => {
  console.log(`Age is ${newAge}`)
})

const increment = () => {
  x.value++;
  y.value++;
}

const changeAge = () => {
  user.age++;
}
</script>

<template>
  <div>
    <!-- <h1 id="count">Count {{ count }}</h1>
    <button @click="count++">Increment</button> -->
    <h1>Watcher</h1>
    <p>Ask a Yes/No Question</p>
    <button @click="increment">Increment</button>
    <p>{{ x }}, {{ y }}</p>
    <button @click="changeAge">Change Age</button>
    <p>{{ user.age }}</p>


  </div>
</template>
