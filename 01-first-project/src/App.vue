<script setup>
import { computed, ref, reactive } from 'vue'
import { useRoute } from 'vue-router'
const isLoggedIn = ref(true)
const toggleLogin = () => {
  isLoggedIn.value = !isLoggedIn.value
}
const userStatus = ref('online')
const changeStatus = () => {
  if (userStatus.value === 'online') {
    userStatus.value = 'away'
  }else if  (userStatus.value === 'away') {
    userStatus.value = 'busy'
  }else if (userStatus.value === 'busy') {
    userStatus.value = 'online'
  }
}

const isVisible = ref(true);
const toggleShow = () => {
  isVisible.value = !isVisible.value
}
</script>

<template>
  <div>
   <h1 v-if="isLoggedIn">Hello logged in user</h1>
   <h1 v-else>Hello new commer</h1>
   <button @click="toggleLogin">{{ isLoggedIn ? 'Log out' : 'Log in' }}</button>
   <br/>
   <h1 v-if="userStatus === 'online'">User is online</h1>
   <h1 v-else-if="userStatus === 'away'">User is away</h1>
   <h1 v-else-if="userStatus === 'busy'">User is busy</h1>
   <h1 v-else>No status</h1>
   <button @click="changeStatus">Change Status</button>
  </div>
  <br>
  <h1 v-show="isVisible">Hidden or Showing</h1>
  <button @click="toggleShow">{{ toggleShow ? 'Show' : 'Hidden'}}</button>

</template>
