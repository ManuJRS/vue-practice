<script setup>
// Crea una variable reactiva llamada message que diga "Hola Vue!" y muéstrala dentro de un <p>.
// Luego, después de 2 segundos, cambia su valor a "Aprendiendo reactividad!".
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