<script setup>
import { onMounted, ref } from 'vue'
const inputRef = ref(null)
const list = ref(['apple', 'banana', 'cherry'])
const itemRefs = ref([])
onMounted(() => {
  inputRef.value.focus()
  itemRefs.value.forEach((item) => {
    item.style.transition = 'opacity 3s'
    item.style.opacity = 1
  })
})
</script>

<template>
  <div>
    <h1>Template refs</h1>
    <input ref="inputRef" />

    <ul>
      <li v-for="(item, index) in list" :key="index" ref="itemRefs" style="opacity: 0">
        {{ item }}
      </li>
    </ul>
  </div>
</template>
