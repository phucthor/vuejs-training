<script setup>
const msg = 'Hello World'
const rawHtml = '<div><h1>Title</h1><span style="color: red">This should be red.</span></div>'
const buttonId = 'button-id'
const buttonClass = 'btn btn-rounded'
const isButtonDisable = false
const objectOfAttrs = {
  id: 'container',
  class: 'wrapper',
  style: 'background-color:green'
}
const number = 0
const listString = 'a, b, c, d, e, f, g'
const convertToId = (data) => data.split(',').reverse().join('-')
const doSomething = () => { alert('Button clicked!') }

const attributeName = 'href'
const url = 'https://www.google.com/'
</script>

<template>
  <h1>Syntax</h1>
  <span>Message: {{ msg }}</span>
  <span v-html="rawHtml"></span>
  <button :id="buttonId" :class="buttonClass" :disabled="isButtonDisable">{{isButtonDisable ? 'Disable' : 'Click here' }}</button>
  <button v-bind="objectOfAttrs">Click me</button>
  <button :id="convertToId(listString)">Number: {{ number + 2 }}</button>
  <button @click="doSomething">Click here</button>
  <a v-bind:[attributeName]="url">Click link</a>
</template>
