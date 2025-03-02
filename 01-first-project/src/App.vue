<script setup>
import { ref, watch } from 'vue'

// const count = ref(0);
// watch(count, (newValue, oldValue) => {
//   console.log('count changed', newValue, oldValue);
// });
const question = ref('')
const isLoading = ref(false)
const answer = ref('')
watch(question, async(newQuestion, oldQuestion) => {
  if (newQuestion.includes('?')) {
    isLoading.value = true
    // setTimeout(() => {
    //   isLoading.value = false;
    // }, 2000);
    answer.value = "Thinking..."
    try {
      const response = await fetch('https://yesno.wtf/api')
      answer.value = (await response.json()).answer
    } catch (error) {
      answer.value = `Error: ${error.message}`
    }
    finally{
      isLoading.value = false
    }
  }
})
</script>

<template>
  <div>
    <!-- <h1 id="count">Count {{ count }}</h1>
    <button @click="count++">Increment</button> -->
    <h1>Watcher</h1>
    <p>Ask a Yes/No Question</p>
    <input v-model="question" :disabled="isLoading" />
    <p>{{ answer }}</p>
  </div>
</template>
