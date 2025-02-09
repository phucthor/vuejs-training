<script setup>
import { computed, ref, reactive } from 'vue'

const text = ref('hi')

const multilineText = ref('')

const checked = ref(false)
const checkedNames = ref([])
const radioChecked = ref()
const selected = ref()
const selectedMultiple = ref([])
</script>

<template>
  <div>
    <h1>Form Input Binding</h1>
    <p>Text: {{ text }}</p>
    <!-- <input :value="text" @input="handleInput"/> -->
    <input v-model="text" />
    <p>Multiline Text: {{ multilineText }}</p>
    <textarea v-model="multilineText" placeholder="Input your massage" />

    <p>Checkbox: {{ checked }}</p>
    <input type="checkbox" v-model="checked" />

    <p>Checkbox: {{ checkedNames }}</p>
    <input type="checkbox" id="a" v-model="checkedNames" value="A" />
    <label for="a">A</label>
    <input type="checkbox" id="b" v-model="checkedNames" value="B" />
    <label for="b">B</label>
    <input type="checkbox" id="c" v-model="checkedNames" value="C" />
    <label for="c">C</label>

    <p>Radio: {{ radioChecked }}</p>
    <input type="radio" id="a" v-model="radioChecked" value="A" />
    <label for="a">A</label>
    <input type="radio" id="b" v-model="radioChecked" value="B" />
    <label for="b">B</label>

    <p>Select: {{ selected }}</p>
    <select v-model="selected">
      <option disabled value="">Please select one</option>
      <option>A</option>
      <option>B</option>
      <option>C</option>
    </select>

    <p>Select Multiple: {{ selectedMultiple }}</p>
    <select v-model="selectedMultiple" multiple>
      <option disabled value="">Please select one</option>
      <option><label for="a">A</label></option>
      <option><label for="b">B</label></option>
      <option><label for="c">C</label></option>
    </select>


  </div>
</template>
