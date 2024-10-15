<template>
  <div class="p-4 grid grid-cols-2 gap-4">
    <form @submit.prevent="submitForm">
      <input v-model="title" placeholder="Titulo del Libro" required>
      <input v-model="author" placeholder="Autor" required>
      <input type="file" @change="onCoverChange" accept="image/*" required>
      <input type="file" @change="onPdfChange" accept="appplication/pdf" required>
      <button type="submit">Registrar Libro</button>
    </form>
  </div>
</template>

<script lang="ts" setup>
import { ref, defineEmits } from 'vue'

interface Book {
  id: number,
  title: string,
  author: string,
  coverUrl: string,
  pdfUrl: string
}

const emit = defineEmits<{
  (e: 'book-added', book: Book): void
}>()

const title = ref('')
const author = ref('')
const cover = ref<File | null>(null)
const pdf = ref<File | null>(null)

const onCoverChange = (e: Event) => {
  const target = e.target as HTMLInputElement
  if (target.files) {
    cover.value = target.files[0]
  }
}

const onPdfChange = (e: Event) => {
  const target = e.target as HTMLInputElement
  if (target.files) {
    pdf.value = target.files[0]
  }
}

const submitForm = () => {
  if (cover.value && pdf.value) {
    const book: Book = {
      id: Date.now(),
      title: title.value,
      author: author.value,
      coverUrl: URL.createObjectURL(cover.value),
      pdfUrl: URL.createObjectURL(pdf.value)
    }
    emit('book-added', book)
    title.value = ''
    author.value = ''
    cover.value = null
    pdf.value = null
  }
}

</script>

<style scoped>
.input {
  width: 100%;
  padding: 0.5rem;
  margin-bottom: 0.5rem;
  border: 1px solid #ddd;
  border-radius: 4px;
}

.button {
  padding: 0.5rem 1rem;
  background-color: #3490dc;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.button.is-ghost {
  background: none;
  color: #3490dc;
  text-align: left;
  padding: 0.25rem;
}

.button.is-ghost:hover {
  background-color: #f5f5f5;
}

</style>