<script setup>
import { ref, onMounted } from 'vue'

const words = ref([])
const error = ref('')

onMounted(async () => {
  try {
    const response = await fetch('https://wordle-backend-ouvv.onrender.com/words')
    words.value = await response.json()
  } catch (e) {
    error.value = 'Wörter konnten nicht geladen werden'
  }
})
</script>

<template>
  <p v-if="error">{{ error }}</p>
  <ul>
    <li v-for="word in words" :key="word.id">{{ word.text }}</li>
  </ul>
</template>