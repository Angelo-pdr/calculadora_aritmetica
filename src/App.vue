<script setup>
import { reactive } from "vue";

const estado = reactive({
  filtro: "Somar",
  resultado: 0,
  numero1: 0,
  numero2: 0,
});

function escolherEquacaoAritmaetica() {
  let { resultado, numero1, numero2, filtro } = estado;
  switch (filtro) {
    case "Somar":
      return (resultado = Number(numero1) + Number(numero2));
    case "Subtrair":
      return (resultado = Number(numero1) - Number(numero2));
    case "Multiplicar":
      return (resultado = Number(numero1) * Number(numero2));
    case "Dividir":
      return (resultado = Number(numero1) / Number(numero2));
    default:
      return resultado;
  }
}
</script>

<template>
  <input
    @keyup="(event) => (estado.numero1 = event.target.value)"
    type="number"
    placeholder="Digite um numero"
  />
  <input
    @keyup="(event) => (estado.numero2 = event.target.value)"
    type="number"
    placeholder="Digite um numero"
  />
  <select
    class="select"
    @change="(event) => (estado.filtro = event.target.value)"
  >
    <option value="Somar">Somar</option>
    <option value="Subtrair">Subtrair</option>
    <option value="Multiplicar">Multiplicar</option>
    <option value="Dividir">Dividir</option>
  </select>
  <p>{{ escolherEquacaoAritmaetica() }}</p>
</template>

<style scoped>
input {
  display: block;
}
</style>
