<script setup>
import { computed, ref, reactive } from 'vue'

const count = ref(0)

const greet = (event) => {
  console.log(event.target);
  // alert(`Hello ${event.type}`)
};

const sayHi = (name) => {
  alert(`Hi ${name}`)
}
</script>


<template>
  <div>
    <h1>Event Handling</h1>
    <button @click="count++">Add 1</button>
    <p>{{ count }}</p>
    <button @click="greet">Hi</button>
    <button @click="sayHi('Tommy')">Hi Tommy</button>
    <button @click="sayHi('John')">Hi John</button>
  </div>
</template>

