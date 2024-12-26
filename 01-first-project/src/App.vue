<script setup>
import { computed, ref, reactive } from 'vue'
const isActive = ref(true)
const hasError = ref(true)
const errorClass = ref('has-error')

// const classObject = reactive({
//   active: true,
//   'has-error': true
// })

const classObject = computed(() => ({
  active: isActive.value && !hasError.value,
  'has-error': hasError.value,
}))

const changeActive = () => {
  isActive.value = !isActive.value
}
</script>

<template>
  <div>
    <button @click="changeActive" class="button" :class="classObject">
      {{ isActive ? 'Active' : 'Deactive' }}
    </button>
    <button
      @click="changeActive"
      class="button"
      :class="[isActive ? 'active' : '', { 'has-error': hasError }]"
    >
      {{ isActive ? 'Active' : 'Deactive' }}
    </button>
  </div>
</template>

<style>
.button {
  border: none;
  background: rgb(136, 0, 48);
  color: rgb(243, 234, 234);
  padding: 10px 14px;
  border-radius: 6px;
  cursor: pointer;
  &:hover {
    background: rgb(245, 82, 109);
  }
}

.active {
  background: rgb(208, 94, 253);
  color: white;
  &:hover {
    background: rgb(174, 103, 202);
  }
}

.has-error {
  background: rgb(255, 0, 85);
  color: rgb(255, 255, 255);
  &:hover {
    background: rgb(228, 57, 86);
  }
}
</style>
