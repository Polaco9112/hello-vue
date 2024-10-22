<template>
  <div>
    <h1 class="title">Calculadora de Impuestos</h1>
    
    <form class="calc">
      <label>Subtotal</label>
      <input type="number" v-model="subtotal">
      <h3>Total de Impuestos: {{ calculateTaxes }} ({{ impuesto }}%)</h3>
    </form>
    
  </div>
</template>

<script lang='ts' setup>
  import {Ref, ref, computed} from 'vue'

  const impuesto = 19

  let subtotal: Ref<number> = ref(0)

  const calculateTaxes = computed(() => (impuesto * subtotal.value) / 100 )
</script>

<style scoped>
  .title{
    text-align: center;
    font-size: 20px;
    font-weight: bold;
  }
  .calc{
    justify-content: center;
    align-items: center;
  }
</style>