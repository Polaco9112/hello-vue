<template>
  <h3>{{ counter }}</h3>
  <button @click="addCounter">Incrementar</button>
  <button @click="resetCounter">Decrementar</button>
</template>

<script lang="ts" setup>
import { Ref, ref } from 'vue';
let counter: Ref = ref(0)
const addCounter = (): void => {
  counter.value++
}
const resetCounter = (): void => {
  counter.value--
}
</script>
