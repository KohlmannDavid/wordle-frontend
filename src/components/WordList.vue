<script setup>
const words = [
  { id: 1, text: 'APFEL' },
  { id: 2, text: 'TISCH' },
  { id: 3, text: 'BROTE' },
]
</script>

<template>
  <ul>
    <li v-for="word in words" :key="word.id">{{ word.text }}</li>
  </ul>
</template>