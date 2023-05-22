<script setup>
import { reactive } from "vue";
import Inputs from "./inputs.vue";
import SelectResult from "./SelectResult.vue";

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
  <div class="container">
    <div class="content">
      <Inputs
        :numero1="(event) => (estado.numero1 = event.target.value)"
        :numero2="(event) => (estado.numero2 = event.target.value)"
      />
      <SelectResult
        :filtro="(event) => (estado.filtro = event.target.value)"
        :MostraResultado="escolherEquacaoAritmaetica()"
      />
    </div>
  </div>
</template>

<style scoped>
.container {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.content {
  padding: 1rem 1.5rem;
  background-color: #252526;
  border-radius: 0.3rem;
  border: 2px solid #3e3e40;
  box-shadow: 3px 3px 3px 3px #a6a6a6;
}
</style>
