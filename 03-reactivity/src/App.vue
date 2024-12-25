<script setup>
import { nextTick, ref } from 'vue'

// const obj = ref({
//   nested: { count: 0 },
//   arr: ['foo', 'bar']
// })

const count = ref(0)

// function mutateDeeply() {
//   // these will work as expected.
//   obj.value.nested.count++
//   obj.value.arr.push('baz')
// }

const increase = async() => {
  count.value++
  console.log(document.getElementById('count').innerText)
  await nextTick()
  console.log(document.getElementById('count').innerText)
}

</script>

<template>
  <div>
    <p id="count">Count: {{ count }}</p>
    <button @click="increase">INC</button>
  </div>
</template>
