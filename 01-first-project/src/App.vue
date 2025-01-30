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
    <!-- <button @click="sayHi1">
      <button @click.stop="sayHi2">Say 2</button>
      Say 1
    </button> -->
    <button @click.self="sayHi1">
      <button @click.self="sayHi2">Say 2</button>
      Say 1
    </button>
    <!-- <form @submit.prevent.stop="submit">
      <button type="submit">Submit</button>
    </form> -->
  </div>
</template>

