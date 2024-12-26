<script setup>
import { computed, ref } from 'vue'

const firstName = ref('Tommy')
const lastName = ref('Nguyen')

const fullName = computed({
  get() {
    return firstName.value + ' ' + lastName.value
  },
  set(newValue) {
    [firstName.value, lastName.value] = newValue.split(',')
  }
})

const changeName = () => {
  fullName.value  = 'Hitle, Jee'
}
</script>

<template>
  <div>
    <p id="count">Full Name: {{ fullName }}</p>
    <p id="count">First Name: {{ firstName }}</p>
    <p id="count">Last Name: {{ lastName }}</p>
    <button @click="changeName">Change Name</button>
  </div>
</template>
