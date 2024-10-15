<template>
  <p :style="{ backgroundColor: '#ccc', color: r}">El mensaje se ha enviado de forma satisfactoria</p>
  <button @click="changeColor">Cambiar Color</button>
</template>

<script lang="ts" setup>
    import {ref} from 'vue'
    let r = ref('red')

    const changeColor = () => {r.value = '#fff'}
</script>

<style>

</style>