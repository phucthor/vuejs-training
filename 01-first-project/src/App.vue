<script setup>
import { onMounted, ref } from 'vue'
const list = ref(['apple', 'banana', 'cherry'])
const itemRefs = ref([])
onMounted(() => {
  console.log(itemRefs.value)
  itemRefs.value.forEach((item) => {
    item.style.transition = 'opacity 3s'
    item.style.opacity = 1
  })
})

const initializeThirdPartyLibrary = (el) => {
  console.log('Hello:', el)
}
</script>

<template>
  <div>
    <h1>Template refs</h1>
    <input
      :ref="
        (el) => {
          initializeThirdPartyLibrary(el)
        }
      "
    />

    <ul>
      <li
        v-for="(item, index) in list"
        :key="index"
        :ref="(el) => (itemRefs[index] = el)"
        style="opacity: 0"
      >
        {{ item }}
      </li>
    </ul>
  </div>
</template>
