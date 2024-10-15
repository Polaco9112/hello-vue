<template>
  <form>
    <input v-model="inputText" type="text" />
    <input v-model="agree" type="checkbox" /> Acepto terminos y condiciones
    <select v-model="country">
      <option value="España">España</option>
      <option value="Ucrania">Ucrania</option>
      <option value="Francia">Francia</option>
    </select>
  </form>
  <h3>{{ inputText }}</h3>
</template>

<script lang="ts" setup>
    import {ref} from 'vue'

    let inputText = ref('')
    let agree = ref(true)
    let country = ref('España')
</script>

<style scoped>
</style>