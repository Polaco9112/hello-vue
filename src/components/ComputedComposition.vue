<template>
  <div>
    <input type="text" v-model="message">
    <h2>{{ message }}</h2>
    <h2>{{ reverse }}</h2>
  </div>
</template>

<script lang="ts">
  import { defineComponent, ref, Ref, computed } from 'vue';

  export default defineComponent({
    name: 'ComputedComposition',
    setup() {
      let message: Ref<string> = ref('')

      const reverse = computed(() => message.value.split('').reverse().join(''))

      return {message, reverse}
    }
  })
</script>

<style scoped>
</style>