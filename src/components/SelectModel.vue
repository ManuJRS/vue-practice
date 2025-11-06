<script setup>
import { ref } from 'vue';
// Crea un <select> con tres opciones: "Rojo", "Verde", "Azul".
// Usa v-model para mostrar debajo un texto que diga:
// "Has elegido el color: Azul" (según la opción seleccionada).
let value = ref("Esperando elección")
const color = {red: 'Rojo', green: 'Verde', blue: 'Azul'}
</script>

<template>
<h1>Elige una opción</h1>
<select name="select" id="" v-model="value" >
    <option disabled value="">-- Elige un color --</option>
    <option value='red' class="rojo">Rojo</option>
    <option value='green' class="verde">Verde</option>
    <option value='blue' class="azul">Azul</option>
</select>

<h2>
    Color Escogido:
    <span :style="{color: value, fontWeight: 'bold'}">{{ color[value] ? color[value] : 'Esperando elección' }}</span>
</h2>

</template>

<style scoped>

.rojo {
    color: red;
}
.verde {
    color: green;
}
.azul {
    color: blue;
}
</style>