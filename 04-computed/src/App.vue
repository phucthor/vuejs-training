<script setup>
import { computed, reactive } from 'vue'

const book = reactive({
  name: 'Book 1',
  chapters: [],
})

const addChapter = () => {
  book.chapters.push('Chapter')
}

const isPublished = computed(() => {
  return book.chapters.length > 0 ? 'Yes' : 'No';
})
</script>

<template>
  <div>
    <p id="count">Book Name: {{ book.name }}</p>
    <p id="count">Released: {{ isPublished }}</p>
    <button @click="addChapter">Add Chapter</button>
  </div>
</template>
