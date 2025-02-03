<script setup>
import { computed, ref, reactive } from 'vue'

const count = ref(0)

const sayHi1 = (name) => {
  alert(`Xin chao 1`)
}

const sayHi2 = (name) => {
  alert(`Xin chao 2`)
}

const submit = () => {
  alert("Form submitted")
}
</script>



<template>
  <div>
    <h1>Event Handling</h1>
    <input @keyup.enter.alt="submit" placeholder="Input your name">
    <button @click.shift="submit">Submit</button>
  </div>
</template>

