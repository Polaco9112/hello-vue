<template>
  <div v-if="book" class="book-viewer">
    <h2>{{ book.title }}</h2>
    <p>Por {{ book.author }}</p>
    <iframe :src="book.pdfUrl" width="100%" height="1500px"></iframe>
  </div>
</template>


<script lang="ts" setup>
  import { defineProps } from 'vue';

  interface Book{
    id: number,
    title: string,
    author: string,
    coverUrl: string,
    pdfUrl: string
  }

  defineProps<{
    book: Book | null
  }>()
</script>

<style scoped>
  .book-viewer{
    margin-top: 20px;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 8px;
  }
</style>