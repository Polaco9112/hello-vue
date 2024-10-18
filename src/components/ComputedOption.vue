<template>
  <div>
    <input type="text" v-model="message">
    <h2>{{ message }}</h2>
    <h2>{{ reverse }}</h2>
  </div>
</template>

<script lang="ts">
  import { defineComponent } from 'vue';

  export default defineComponent({
    name: 'ComputedOption',
    data () {
      return {message : ''}
    },
    computed: {
      reverse(): string {
        return this.message.split('').reverse().join('')
      }
    }
  })
</script>

<style scoped>
</style>