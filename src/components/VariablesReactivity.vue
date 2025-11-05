<script setup>
import { ref } from 'vue'; 

ref
let message = ref("Hola Vue")

setTimeout(() => {
  message.value = "Adios vue"
}, 3000);

</script>

<template>
  <h1>esto es una prueba</h1>
  <p>{{ message }}</p>
</template>