<script setup>
 const props = defineProps(["numero1", "numero2"])

</script>

<template>
      <input
        @keyup="props.numero1"
        type="number"
        placeholder="Digite um numero"
      />
      <input
        @keyup="props.numero2 "
        type="number"
        placeholder="Digite um numero"
      />
</template>

<style scoped>

input {
  display: block;
  width: 100%;
  padding: .3rem .5rem;
  margin: .2rem 0px;
  background-color: #A6A6A6;
  border: none;
  border-radius: .3rem;
  outline: none;
  color: white;
}

</style>
