<template>
  <ComputedComposition />
</template>

<script lang="ts" setup>
  // import ClassBind from './components/ClassBind.vue'
  import ComputedComposition from './components/ComputedComposition.vue';
</script>

<style>
</style>




<!-- <template>
  <div id="app">
    <h1>Biblioteca de Libros</h1>
    <div class="container">
      <div class="left-section">
        <BookForm @book-added="addBook" />
        <BookList :books="books" @select-book="selectBook" />
      </div>
      <div class="right-section">
        <BookViewer :book="selectedBook" />
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import BookForm from './components/BookForm.vue'
import BookList from './components/BookList.vue'
import BookViewer from './components/BookViewer.vue'

interface Book {
  id: number;
  title: string;
  author: string;
  coverUrl: string;
  pdfUrl: string;
}

const books = ref<Book[]>([])
const selectedBook = ref<Book | null>(null)

const addBook = (book: Book) => {
  books.value.push(book)
}

const selectBook = (book: Book) => {
  selectedBook.value = book
}
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

h1 {
  color: #2c3e50;
  text-align: center;
}

.container{
  display: flex;
  flex-direction: row;
  height: 100vh;
  gap: 40px;
}

.left-section{
  display: flex;
  width: 30%;
  flex-direction: column;
  gap: 10px;
}

.right-section{
  width: 70%;
}

/* Estilos adicionales para mejorar la apariencia general */
button {
  background-color: #4CAF50;
  border: none;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  border-radius: 4px;
}

input[type="text"],
input[type="file"] {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}
</style> -->