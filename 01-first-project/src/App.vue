<script setup>
import { computed, ref, reactive } from 'vue'

const text = ref('hi')

const multilineText = ref('')

// const handleInput = (e) => {
//   // console.log(e)
//   text.value = e.target.value
// }
</script>



<template>
  <div>
    <h1>Form Input Binding</h1>
    <p>Text: {{ text }}</p>
    <!-- <input :value="text" @input="handleInput"/> -->
     <input v-model="text">
     <p>Multiline Text: {{ multilineText }}</p>
     <textarea v-model="multilineText" placeholder="Input your massage"/>
  </div>
</template>

