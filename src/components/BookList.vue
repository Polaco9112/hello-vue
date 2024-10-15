<template>
  <div class="book-list">
    <div v-for="book in books" :key="book.id" class="book-card" @click="selectBook(book)">
      <img :src="book.coverUrl" :alt="book.title">
      <h3>{{ book.title }}</h3>
      <p>{{ book.author }}</p>
    </div>
  </div>
</template>

<script lang="ts" setup>
  import { defineProps, defineEmits } from 'vue';

  interface Book{
    id: number,
    title: string,
    author: string,
    coverUrl: string,
    pdfUrl: string
  }

  const props = defineProps<{
    books: Book[]
  }>()

  const emit = defineEmits<{
    (e: 'select-book', book: Book): void
  }>()

  const selectBook = (book: Book) => {
    emit('select-book', book)
  }

</script>

<style scoped>
  .book-list{
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .book-card{
    width: 200px;
    cursor: pointer;
  }

  .book-card img{
    width: 100%;
    height: 300px;
    object-fit: cover;
  }
</style>