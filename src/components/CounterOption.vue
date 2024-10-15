<template>
  <div class="counter-container">
    <h3>{{ counter }}</h3>
    <button @click="addCounter">Incrementar</button>
    <button @click="resetCounter">Decrementar</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'CounterOption',
  data() {
    let counter = 0;
    return { counter }
  },
  methods: {
    addCounter() {
      this.counter++
    },
    resetCounter() {
      this.counter--
    }
  },
})
</script>

<style>
  .counter-container{
    align-items: center;
  }
</style>