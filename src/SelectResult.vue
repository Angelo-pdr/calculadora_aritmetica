<script setup>
const props = defineProps(["filtro", "MostraResultado"]);
</script>

<template>
  <div class="selectResult">
    <select class="select" @change="props.filtro">
      <option value="Somar">Somar</option>
      <option value="Subtrair">Subtrair</option>
      <option value="Multiplicar">Multiplicar</option>
      <option value="Dividir">Dividir</option>
    </select>
    <p>Resultado: {{ props.MostraResultado }}</p>
  </div>
</template>

<style scoped>
.selectResult {
  display: flex;
  align-items: center;
  justify-content: space-between;
  color: white;
}

.select {
  color: white;
  outline: none;
  background-color: #a6a6a6;
  border: none;
  border-radius: 0.3rem;
  cursor: pointer;
}
</style>
