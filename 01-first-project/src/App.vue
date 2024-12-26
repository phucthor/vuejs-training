<script setup>
  import { computed, ref, reactive } from 'vue';
  const isActive = ref(true)
  const hasError = ref(true)

  // const classObject = reactive({
  //   active: true,
  //   'has-error': true
  // })

  const classObject = computed(() => ({
    active: isActive.value && !hasError.value,
    'has-error': hasError.value
  }))
  
</script>

<template>
  <div>
    <button class="button" :class="classObject">Active</button>
  </div>
</template>

<style>

  .button {
    border: none;
    background: rgb(230, 192, 205);
    color: rgb(207, 88, 88);
    padding: 10px 14px;
    border-radius: 6px;
    cursor: pointer;
    &:hover {
      background: rgb(230, 224, 225);
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